# nvm (Node Version Manager)

Az nvm segít telepíteni a Node (és az npm) egy adott verzióját, vagy könnyen váltani a telepített verziók között.

Az nvm telepítése (Linux parancssorban, vagy Windows-on Git Bash-ben):

- másold be a parancsot az nvm GitHub oldaláról
- amit kiír a parancs a telepítés után három parancsot, azokat másold ki és futtasd le (másold be újra a parancssorba) VAGY indítsd újra a terminált

A Node-ot az nvm segítségével a következő paranccsal telepítheted:

```bash
nvm install stable
```

Ez a legutóbbi stabil verziót fogja telepíteni.

Ha egy másik verziót szeretnél telepíteni, akkor a `stable` helyett a verziószámot írd be, pl.:

```bash
nvm install 18
nvm install 18.0.2
```

A telepített verziók között a következő paranccsal váltani tudsz:

```bash
nvm use 18
```

A telepített verziók listáját a következő paranccsal írathatod ki:

```bash
nvm ls

# vagy
nvm list
```

