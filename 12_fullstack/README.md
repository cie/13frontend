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

- php artisan make:controller AuthController
- routes/api.php 

    Route::post('/signup', [AuthController::class, 'signup']);

- AuthController.php - TODO majd  https://laravel.com/docs/11.x/authentication#authenticating-users alapján csináljuk a logint
   
    public function signup(Request $request) {
        // először csak próbaképp:
        return response()->json(['ok' => true]);
    }
