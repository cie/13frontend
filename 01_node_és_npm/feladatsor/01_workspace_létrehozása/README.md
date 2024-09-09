# Workspace létrehozása

Regisztrálj a https://coder.launchpad.hu címen, és hozz létre egy új workspace-t. A workspace neve legyen `frontend`.

Ha létrejött, nyisd meg az IDE-t a "code-server" gombbal (vagy esetleg csatlakozz saját gépedről az Open in VS Code gombbal).

**Ha valami hiba miatt nem sikerül, hagyd ki ezt a fejezetet, és a saját gépeden folytasd a feladatokat.**

Ez egy böngészőből futó VSCode és alatta egy linux környezet (igazából egy docker konténer). Nyisd meg a terminált, és futtasd le a következő parancsokat:

```bash
ls .
ls . -a
ls /
mkdir test
echo "Hello, world!" > test/hello.txt
cd test
ls
cat hello.txt
```

Ha bármelyik parancs jelentése nem világos, nyugodtan kérdezz!
