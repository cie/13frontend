# Fullstack autentikáció

https://laravel.com/docs/11.x/sanctum#spa-authentication alapján

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

       
      http.get('http://backend.vm1.test/sanctum/csrf-cookie')

- php artisan make:controller AuthController
- routes/api.php 

    Route::post('/signup', [AuthController::class, 'signup']);

- AuthController.php - TODO majd  https://laravel.com/docs/11.x/authentication#authenticating-users alapján csináljuk a logint
   
    public function signup(Request $request) {
        return response()->json(['ok' => true]);
    }
