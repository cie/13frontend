Készítettem egy Google Scriptet a helyettesítések lekérdezésére:

```javascript

```

1. Valamelyik korábbi Vite-es projektedben írj egy szkriptet egy .js fájlba, ami az oldal betöltődésekor lekéri `fetch` függvénnyel a https://script.google.com/macros/s/AKfycbzAwQ5zVV2spxCniFeMkSK0_6e-ADdP6vLVJ_fhAiKoegus7EMgnidxHwjV4ekM_J1K/exec endpointról a helyettesítéseket, és kilogolja. Csak akkor fut le a .js fájl, ha az index.html behívja.

2. A fetch nagyon jó és hasznos függvény de egy picit kényelmesebb használni az Axios-t. Telepítsd a projektbe az Axios-t `npm install axios` paranccsal, és használd ezt a helyettesítések lekérdezésére. Nézd meg a dokumentációt, hogy hogyan tudod használni egy GET kéréshez. A kapott JSON-t ugyanúgy logold ki.

3. A harmadik oszlop tartalmazza az óra idejét. Logold ki csak azokat, amik még nem értek véget. Használd az Array `.filter()` metódust. Ahhoz, hogy egy sorról eldöntsd, bontsd fel a harmadik oszlop sztringjét a '-' mentén (`.split()`), majd a végidőpontot a ':' mentén. A jelenlegi időhöz használd a `Date` osztályt és metódusait.

4. Ezt a JSON adatstrukúrát kell majd megjeleníteni az alkalmazás felületén egy szépen megformázott táblázatban. Csinálhatnánk közvetlen DOM manipulációkkal, de nehézkes lenne a táblázatot megfelelő módon frissíteni (ahogy telik az idő, egyre kevesebb sort kell megjeleníteni).

   Erre való a Vue.js (és más hasonló könyvtárak, React, Angular stb.) - hogy nyers adatokat HTML DOM struktúrába képezze le, és ha az adatok változnak, akkor frissítse.

   Kezdj egy új projektet az `npm create vite helyettesites` paranccsal, és amikor kérdezi, Vue-t válassz, azon belül JavaScript-et. A parancsot a többi projekteden kívüli könyvtáradban add ki, ne egy másik projekt könyvtárán belül, mert akkor abba teszi.

   Ahogy kéri, lépj bele a könyvtárba, futtass npm install-t és npm run dev-et. A böngészőben megjelenik a Vue alap projektje.

   Jelenítsd meg egy táblázatban a leszűrt helyettesítéseket.
