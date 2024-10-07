# Vue alapok

Az Options API-t használd az alábbiak megoldásánál.

Hozz létre egy új vue projektet `vue_alapok` néven az `npm create vite vue_alapok` parancs segítségével. Vue-t és JavaScript-et válassz. Vigyázz, ne egy másik projektben futtasd!

Lépj bele, és `npm install`, majd `npm run dev`.

Telepítsd a Tailwind-et a projektbe a https://tailwindcss.com/docs/guides/vite#vue oldal alapján a 2. ponttól.

Az App komponensből töröld ki a `<style setup>`-ból a `setup`-ot és a fölösleges tartalmakat, a style.css-ből is mindent, ami nem a tailwind három sora.

1. Reaktív állapot és eseménykezelés

   Készíts egy reaktív állapotot! Az App komponensben

   ```javascript
   export default {
     data() {
       return {
         count: 0,
       };
     },
   };
   ```

   Tegyél az oldalra egy gombot és egy számlálót. A gombra kattintva a számláló nőjön eggyel. Ne a HelloWorld.js-ben lévő megoldást használd, mert az a Composition API-t használja.

2. Feltételes renderelés

   Tegyél az oldalra egy checkbox-ot, ami mondjuk a szerződéses feltételek elfogadását jelenti. Amikor nincs kipipálva, jelenjen meg egy figyelmeztető szövegdoboz. Amikor kipipálja a felhasználó, tűnjön el, ha kiveszi a pipát, újra jelenjen meg. A szövegdoboznak adj halvány háttérszínt, némi paddinget és egy színes bal border-t a Tailwind segítségével.

   Ehhez vezess be egy új reaktív állapotot, boolean típusút. A szövegdobozhoz használj `v-if` direktívát.

3. Animáció

   Készíts a fenti szövegdoboznak CSS animációt! Ehhez legegyszerűbben az kell, hogy kikapcsolt állapotban is renderelve legyen (bekerüljön a DOM-ba), és a style segítségével állítsd az opacity tulajdonságot a reaktív állapot függvényében 0-ra vagy 1-re. Ehhez használd a `:style` binding-ot. Állítsd be a következő CSS-eket:

   ```css
   transition-property: opacity, transform;
   transition-duration: 0.3s;
   ```

   Így már az opacity animálva lesz, szépen elő-és eltűnik. A transform tulajdonságot is állítsd be valamire kikapcsolt állapot esetén (pl. `translate(-5px, 0)` vagy `scale(0.9)`), így egy pici mozgás is lesz benne.

4. Szovegdoboz tartalma

   Készíts két szövegdobozt, ami mindig ugyanazt tartalmazza. Ehhez vegyél fel egy új reaktív állapotot, sztring típusút, ami tartalmazza a szöveget. Mindkét doboz értékét kösd ehhez (`:value` direktívával). És mindkét dobozra tegyél eseménykezelőt, hogy amikor változik (input esemény, `@input` direktíva), az állapot is változzon.

   Ha ez sikerült, az egyik szövegdoboznál cseréld le a megoldást `v-model` direktívára, és ellenőrizd, hogy így is működik.

5. Class-ok kapcsolása reaktív állapot alapján

   Készíts egy mini stílus-állító űrlapot! Legyen egy szöveg, aminek a különböző Tailwind-osztályait lehet ki-be kapcsolni egy-egy checkboxszal:

   - vastag betű
   - dőlt betű
   - nagyobb betű
   - piros szín

   Használd a `:class` direktívát, és a Tailwind `font-bold`, `italic`, `text-lg` és `text-red-500` osztályait.
