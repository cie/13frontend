# npm install

A `package.json` fájlban található `dependencies` és `devDependencies` megmutatja, hogy mely más csomagokra van szükségünk a mi csomagunk futtatásához ill. fejlesztéséhez.

Az összes függőség (szükséges csomag) telepítéséhez (pl miután git-ből klónoztuk a projektet, mivel általában a git-ben nem tároljuk a függőségeket):

```bash
$ npm install
# VAGY
$ npm i
```

A csak a `dependencies`-ben szereplők telepítéséhez (a `devDependencies`-ben szereplők nélkül):

```bash
$ npm install --production
```

A függőségek (szükséges csomagok) a `node_modules` mappába kerülnek.

Új függőség hozzáadása:

```bash
$ npm add <csomagnev>
# VAGY
$ npm install <csomagnev>
# VAGY
$ npm i <csomagnev>
```

(Az `npm add` és `npm install` ugyanaz)

Új dev függőség hozzáadása:

```bash
$ npm add -D <csomagnev>
# VAGY
$ npm install -D <csomagnev>
# VAGY
$ npm i -D <csomagnev>
```
