## Autorizáció

Nem csupán azt kell tudnunk biztosra, hogy ki a felhasználó – ez az autentikáció –, hanem azt is meg kell mondanunk, hogy ez felhasználó mit tehet és mit nem: ez az autorizáció.

Tehát: a felhasználó csak azokat a todo-kat szerkeszthesse, amik a sajátjai.

Ehhez először is fel kell venni egy `user_id` sztring mezőt a Todos táblába:
```
            $table->string('user_id');
```
Ezután a seederbe vagy factorybe is fel kell venni, hogy egy meglévő user-hez kösse. 
A DatabaseSeeder alapból létrehoz nekünk egy felhasználót, de oldd meg, hogy 3-at hozzon létre.
Ezután a todo seederünkben vagy factorynkban kössük be ezek közül valamelyiket.

            'user_id' => fake()->randomElement([1,2,3]),

A https://laravel.com/docs/11.x/authorization alapján készíts el három gate-et:

```
        Gate::define('update-todo', function (User $user, Todo $todo) {
            return $user->id === $todo->user_id;
        });
        Gate::define('show-todo', function (User $user, Todo $todo) {
            return $user->id === $todo->user_id;
        });
        Gate::define('destroy-todo', function (User $user, Todo $todo) {
            return $user->id === $todo->user_id;
        });
```

és ezeket használd a TodosController metódusaiban.

Az `index` metódusban csak azokat a todokat küldd le, amiket a felhasználó sajátja.

A `store` metódusban mentsd le a user_id-t.

Teszteld az összes metódust, hogy csak a megfelelő felhasználó fér hozzá.
