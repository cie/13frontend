# .gitignore

A `.gitignore` fájlban olyan fájlokat és könyvtárakat sorolunk fel, amelyeket a Git figyelmen kívül hagy, nem fogja véletlenül hozzáadni a repóhoz.

A `node_modules` mappába kerülnek az npm által telepített csomagok. Ezeket nem szokás feltölteni a Git-repóba, mert nagy mérteűek lehetnek, és a `package.json` fájlban fel vannak sorolva, így a `npm install` paranccsal bármikor könnyen újra telepíthetőek.

Hozz létre egy `.gitignore` fájlt a projekted gyökérkönyvtárában, és írd bele a következőt:

```
node_modules
```
