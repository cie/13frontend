# Menetrendjelző képernyő

Készíts egy weblapot, amit akár az iskola bejáratához egy képernyőre ki lehetne tenni, ami mutatja, hogy
mikor jön a következő 80-as troli az Örs vezér tere felé.

## Alapok

- hozz létre egy új mappát, lépj bele, és `npm init`-tel hozz létre egy npm csomagot
- `npm install -D vite`-tel telepítsd a Vite-et
- hozz létre egy `index.html` fájlt
- `npx vite` paranccsal indítsd el a Vite fejlesztői szervert, és nyisd meg
- .gitignore-ba vedd fel a `node_modules` mappát
- kommitold az eddigieket, és egy új github repóba pushold fel

## JSON kapcsolódás

- keresd ki, hogy hogyan lehet a BKK futár API-ját meghívni (pszt, itt egy API kulcs, vigyázz rá: 85144c43-41fc-4a25-ac23-85626ae4c46f, itt egy másik: 335104a7-c630-4088-84b2-bc4b8524ee9c)
  - teszteléshez használhatod ezt az endpointot, ami egy hasonló JSON-t ad vissza: http://coder.launchpad.hu:8080/80.json
- készíts egy `bkk.js` fájlt, amiben egy függvény van, ami visszaadja a következő 80-as troli érkezési idejét
- állítsd be, hogy 1 percenként betegye az eredményt az olda törzsébe

## Stílus

- formázd meg az oldalt CSS-sel
