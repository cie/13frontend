# Tailwind

Mai órán a workspace-ben fogunk dolgozni (https://coder.launchpad.hu), és egyelőre nem a közös projekten, hanem a Tailwind-et fogjuk megismerni.

1. Talán emlékszel Bootstrap-ben az ún. Utility osztályokra. Például a `d-flex` a display-t flex-re állítja, míg a `mr-3` osztály egy jobb oldali margót állít be. Csináljunk ebből egy ismétlést!

   - Hozz létre egy új mappát `bootstrap-utilities` néven, és nyisd meg ezt VSCode-ban az Open folder-rel
   - Hozz létre benne egy npm csomagot `npm init`-tel
   - Add hozzá a vite-et `npm install -D vite`-tel (a -D azért, hogy csak a fejlesztői függőségekbe kerüljön be)
   - Indítsd el a vite-et `npx vite`-tel
   - Hozz létre egy index.html-t a következő tartalommal:

     ```html
     <!DOCTYPE html>
     <html>
       <head>
         <meta charset="utf-8" />
         <title>Bootstrap Utilities</title>
         <link
           rel="stylesheet"
           href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
         />
       </head>
       <body>
         <p>
           Siker! Állítsd ennek a bekezdésnek a szövegét `success` színűre!
           <a href="https://getbootstrap.com/docs/5.0/utilities/colors/"
             >https://getbootstrap.com/docs/5.0/utilities/colors/</a
           >
         </p>
         <p>
           Ennek a bekezdésnek adj keretet!
           <a href="https://getbootstrap.com/docs/5.0/utilities/borders/"
             >https://getbootstrap.com/docs/5.0/utilities/borders/</a
           >
         </p>
         <p>
           Ennek a bekezdésnek adj egy nagyobb felső margót!
           <a href="https://getbootstrap.com/docs/5.0/utilities/spacing/"
             >https://getbootstrap.com/docs/5.0/utilities/spacing/</a
           >
         </p>
       </body>
     </html>
     ```

   - Végezd el a html szövegében lévő három feladatot, és ellenőrizd az eredményt az oldalt megnyitva.

2. A Bootstrap-ben ezek a utility osztályok kis segítségként vannak betéve, hogy ha egy-két dolgot át kell állítani, azokat könnyen át tudd (ne kelljen CSS-t írni, elég egy-egy osztályt betenni).

   A Tailwind keretrendszer ezzel szemben _elsősorban_ utility osztályokból épül fel ("utility-first").

   Nézd meg az animációt a [Tailwind honlapján](https://tailwindcss.com), és értsd meg, hogy mi történik, ahogy szerkeszti a css osztályokat.

3. Hozz létre újra egy új mappát `tailwind-1` néven, lépj át bele a VS Code-dal, és a fenti módon telepítsd benne a Vite-et.

4. Telepítsd a Tailwind-et a Vite-be: https://tailwindcss.com/docs/guides/vite - ezen belül a 2-5 pontok.

5. Hozz létre egy index.html-t a következő tartalommal, és oldd meg ezeket a feladatokat!

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Tailwind basics</title>
    <link rel="stylesheet" href="./src/index.css" />
  </head>
  <body>
    <p>
      Siker! Állítsd ennek a bekezdésnek a szövegét piros színűre! Keresd ki a
      Tailwind dokumentációból!
    </p>
    <p>Ennek a bekezdésnek adj 2px vastag kék keretet!</p>
    <p>Ennek a bekezdésnek adj hátteret és paddinget!</p>
  </body>
</html>
```

6. Készítsd el a Tailwind segítségével ezt a dizájnt: https://iho.hu/img/vasut/1207/120718_tarnok/kl/814/P8221191.jpg NEM kell, hogy friss adatokkal dolgozzon!

   CSS grid tutorial: https://cssgridgarden.com/#hu
