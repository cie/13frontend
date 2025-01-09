# 1. Card

Készíts egy Card komponenst, ami egy doboz árnyékkal. Lehessen megadni címet prop-ban. Így lehessen használni például:

```
<Card title="Személyes adatok">
  <div>Email <input></div>
  <div>Telefonszám<input></div>
</Card>
<Card title="Számlázási adatok">
  <div>Cégnév <input></div>
  <div>Cím<input></div>
</Card>
```

# 2. Details

Készíts egy Details komponenst, ami egy doboz, aminek kezdetben csak a címe látszik. A címére kattintva viszont jelenjen meg a tartalma. A felső sarokban egy ikon jelezze, hogy ki lehet nyitni vagy be lehet csukni.

```
<Details title="Személyes adatok">
  <div>Email <input></div>
  <div>Telefonszám<input></div>
</Details>
<Details title="Számlázási adatok">
  <div>Cégnév <input></div>
  <div>Cím<input></div>
</Details>
```

A komponensnek legyen egy belső állapota (amit a `<script setup>`-ban a `ref()`-fel tudsz létrehozni), boolean típusú, ami tárolja, hogy nyitva van-e vagy csukva.

# 3. Accordion

Készíts egy Accordion komponenst, ami kinyitható paneleket fog össze.

```
<Accordion>
  <AccordionPane title="Személyes adatok">
    <div>Email <input></div>
    <div>Telefonszám<input></div>
  </AccordionPane>
  <AccordionPane title="Számlázási adatok">
    <div>Cégnév <input></div>
    <div>Cím<input></div>
  </AccordionPane>
</Accordion>
```

A következő cél az lesz, hogy egyszerre egy komponens lehessen nyitva. Emiatt valahogy a külső Accordion komponensnek is kell legyen egy "közös" állapota, ami az AccordionPane-ekre is hatással van.
Viszont előbb csináljunk valamit, amitől ez könnyebb lesz...

# 3. Store

Térjünk vissza egy kicsit a Details feladathoz, mert az egyszerűbb, és azt alakítsuk át.

Ahogy eddig csináltuk, kicsit keveredik a komponens *kinézete* és *működése*. Ilyen egyszerűbb komponenseknél nem gond, de bonyolultabb esetben hasznos
lehet különválasztani. Válasszuk külön egy külön fájlba a működését: azaz a reaktív állapotot (`ref()`-et) és azt a függvényt, ami ezt ki/be kapcsolja (legyen `toggle`).

Hogyan tudjuk ezt szépen? Normál JavaScriptben az adatok és műveletek egybecsomagolására jó a class. Vue-ban a reaktív állapotok, számított értékek és műveletek egybecsomagolására jó a *store*, amit a Pinia csomag ad.

Telepítsd a `pinia` csomagot, és a https://pinia.vuejs.org/core-concepts/#Setup-Stores alapján készíts egy store-t a Details komponens `<script setup>`-jában, valahogy így:

```





