# Tailwind

Mai órán a workspace-ben fogunk dolgozni (https://coder.launchpad.hu), és egyelőre nem a közös projekten, hanem a Tailwind-et fogjuk megismerni.

1. Talán emlékszel Bootstrap-ben az ún. Utility osztályokra. Például a `d-flex` a display-t flex-re állítja, míg a `mr-3` osztály egy jobb oldali margót állít be. Csináljunk ebből egy ismétlést!

   - Hozz létre egy új mappát `bootstrap-utilities` néven, és nyisd meg ezt VSCode-ban az Open folder-rel
   - Hozz létre benne egy npm csomagot `npm init`-tel
   - Add hozzá a vite-et `npm install -D vite`-tel (a -D azért, hogy csak a fejlesztői függőségekbe kerüljön be)
   - Indítsd el a vite-et `npx vite`-tel
   - Hozz létre egy index.html-t a következő tartalommal:

     ```html
     <!doctype html>
     <html>
       <head>
         <meta charset=utf-8>
         <title>Bootstrap Utilities</title>
         <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css">
       </head>
       <body>
          <p>Siker! Állítsd ennek a bekezdésnek a szövegét `success` színűre! <a href="https://getbootstrap.com/docs/5.0/utilities/colors/">https://getbootstrap.com/docs/5.0/utilities/colors/</a></p>
          <p>Ennek a bekezdésnek adj keretet! <a href="https://getbootstrap.com/docs/5.0/utilities/borders/">https://getbootstrap.com/docs/5.0/utilities/borders/</a></p>
          <p>Ennek a bekezdésnek adj egy nagyobb felső margót! <a href="https://getbootstrap.com/docs/5.0/utilities/spacing/">https://getbootstrap.com/docs/5.0/utilities/spacing/</a></p>
       </body>
     </html>
     ```

   - Végezd el a html szövegében lévő három feladatot, és ellenőrizd az eredményt az oldalt megnyitva.
    
2. A Bootstrap-ben ezek a utility osztályok kis segítségként vannak betéve, hogy ha egy-két dolgot át kell állítani, azokat könnyen át tudd (ne kelljen CSS-t írni, elég egy-egy osztályt betenni).

   A Tailwind keretrendszer ezzel szemben *elsősorban* utility osztályokból épül fel ("utility-first").

   Nézd meg az animációt a [Tailwind honlapján](https://tailwindcss.com), és értsd meg, hogy mi történik, ahogy szerkeszti a css osztályokat.

   
