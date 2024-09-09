# package.json

A `package.json` fájl jelzi egy mappában, hogy ez egy NodeJS csomag. Általában a NodeJS projektünk egyben NodeJS csomag is, azaz van a projektünk gyökérkönyvtárában egy `package.json` fájl.

## Miket tartalmaz?

### A csomag adatai

- neve
- verziója
- leírása
- ki készítette
- licensz
- git repó elérhetősége

### Szkriptek (`scripts`)

Ezek olyan segédparancsok, amiket a `npm run` paranccsal futtathatunk. Például:

```json
  "scripts": {
    "start": "node index.js",
    "test": "mocha tests"
  }
```

ezeket így futtathatjuk:

```bash
$ npm run start
$ npm run test
```

### Függőségek (`dependencies` és `devDependencies`)

Megmutatja, hogy mely más csomagokra van szükségünk a mi csomagunk működéséhez. 
- a `dependencies`-ben azok a csomagok vannak, amik a futtatáshoz szükségesek,
- a `devDependencies`-ben pedig azok, amik csak a fejlesztéshez, a futtatáshoz nem.
