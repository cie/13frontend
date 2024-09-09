# gitignore fájl NodeJS projektekben

A `.gitignore` fájlban olyan fájlokat és mappákat sorolhatunk fel, amiket nem szeretnénk a git repóba kommitolni.

Érdemes ide felvenni a `node_modules` mappát, mert a NodeJS csomagok sok helyet foglalhatnak, és bármikor újra le lehet tölteni őket, ezért általában nem szeretnénk őket a git repóba kommitolni. Pl. ezek lehetnek a .gitingore fájlban:

```gitignore
node_modules
dist
.DS_Store
```

(`dist`-nek szokták hívni azt a mappát, amiben a forráskódból összeépített futtatható kód van. Mivel ez bármikor újragenrálható a forráskódból, ezért nem szokás a git repóban tárolni.)

(A .DS_Store nevű mappát MacOS rendszeren a Finder hozza létre, nem érdemes a git repóba betenni, ezért érdemes lehet felvenni a .gitignore-ba.)
