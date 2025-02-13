# Fullstack autentikáció

https://laravel.com/docs/11.x/sanctum#spa-authentication alapján

- pages/signup.vue

```html
<script setup>
import { ref } from 'vue';
import { http } from '../utils/http.mjs'

const email = ref('');
const password = ref('');

function submit() {
  http.post('/signup', {
    email: email.value,
    password: password.value,
  })
}
</script>

<template>
  <div class="flex flex-col p-4">
    <input v-model="email" placeholder="Your email" type="email"/>
    <input
      v-model="password"
      placeholder="Your password"
      type="password"
      @keypress.enter="submit"
    />
    <button class="bg-blue-500 text-white" @click="submit">
      Sign up
    </button>
  </div>

</template>
```  

- pages/login.vue hasonlóan

- frontend címét .env-ben SANCTUM_STATEFUL_DOMAINS-ben
- bootstrap/app.php

      ->withMiddleware(function (Middleware $middleware) {
        $middleware->statefulApi();
      })

- php artisan config:publish cors
- config/cors.php:     'supports_credentials' => true,
- frontend http.mjs-ben:

       withCredentials: true,
       withXSRFToken: true,

- A CSRF kódot el kell kérni minden más kérés előtt. A frontend http.mjs-ben:
       
      await http.get('sanctum/csrf-cookie')

- Azonban a fenti sor "api/sanctum/csrf-cookie"-t kéri le, pedig "sanctum/csrf-cookie" kell. Az egyszerűség kedvéért oldjuk meg, hogy valóban "api/sanctum/csrf-cookie" címen legyen elérhető a sanctum:  config/sanctum.php:

      'prefix' => 'api/sanctum'

- Ezután a [Fortify](https://laravel.com/docs/11.x/fortify#installation)-t fogjuk használni az autentikációhoz.
    -  composer require laravel/fortify
    - php artisan fortify:install
    - php artisan migrate
- A fortify config fájlban kapcsoljuk ki a views-t, hiszen most nem Laravelben van a frontend. A features-ben sem kell two-factor stb. csak ezek:

      'views' => false,
  
      'features' => [
          Features::registration(),
          Features::resetPasswords(),
          Features::emailVerification(),
      ],

- Ugyanitt állítsuk be a 'prefix'-et '/api'-ra, hogy ne '/login' és '/register', hanem '/api/login' és '/api/register' legyen (ezzel rendezettebb lesz, és /api alatt a sanctum beállítja a CORS-ot, így elérhető lesz a frontend js-nek)
- mivel a Fortify /signup helyett /register-nek hívja a regisztráció API elérési útját, ezt javítsuk a signup.vue-ban
- Teszteljük a regisztrációt.
- A password_confirmation-t hiányolni fogja a Fortify. Ha szeretnénk, csináljunk egy ennek megfelelő mezőt, VAGY ha nem, küldjük el password_confirmation néven is a passwordöt
- A Fortify hiányolja a "name"-et regisztrációnál. Csináljunk egy ilyen mezőt.

- Ha most teszteljük a formot, elvileg már sikeresen regisztrál, egy üres sztringet ad vissza válasznál. Ezt majd szeretnénk testreszabni, hogy a user-t adja vissza.
- A loginnál rosszabb a helyzet: loginel DE utána redirektel a főoldalra (mint egy normális backend MVC alkalmazás). Ez nekünk nem jó, hiszen ez egy single-page application, nincs is főoldala a backendnek! Úgyhogy módosítsuk a Fortify működését, hogy mit válaszoljon a login és logout kérésekre - JSON-t. Ezt a FortifyServiceProvider-ben tehetjük meg.

```
use Laravel\Fortify\Contracts\LoginResponse;
use Laravel\Fortify\Contracts\LogoutResponse;
use Laravel\Fortify\Contracts\RegisterResponse;
use Laravel\Fortify\Fortify;

class FortifyServiceProvider extends ServiceProvider
{
    /**
     * Register any application services.
     */
    public function register(): void
    {
        $this->app->instance(LoginResponse::class, new class implements LoginResponse {
            public function toResponse($request)
            {
                return response()->json($request->user());
            }
        });
        $this->app->instance(LogoutResponse::class, new class implements LogoutResponse {
            public function toResponse($request)
            {
                return response()->json($request->user());
            }
        });
        $this->app->instance(RegisterResponse::class, new class implements RegisterResponse {
            public function toResponse($request)
            {
                return response()->json(['ok' => true]);
            }
        });
    }
```

- Ellenőrizd a Network fülön tesztelted a register-t és a login-t, hogy visszakapod az usert a json-ben
- Ebben a user objektumban viszont szenzitív autentikációs adatok is vannak, amiket nem szeretnénk leküldeni. Ezért definiálni kéne, hogy miket szeretnénk leküldeni... egy resource-ban:

      php artsian make:resource UserResource

- Állítsd be a resource-t úgy, hogy csak a fontos adatokat küldje le, és módosítsd a fenti metódusokat úgy, hogy a Response-t használják.
  

<div>
<!--
-  ->middleware('auth:sanctum');
-->
</div>
