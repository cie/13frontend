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

# 4. Közös állapot

A következő cél az lesz, hogy egyszerre egy komponens lehessen nyitva. Emiatt valahogy a külső Accordion komponensnek is kell legyen egy "közös" állapota, ami az AccordionPane-ekre is hatással van.

Készíts az Accordion komponensben egy reaktív állapotot (pl. `activePane`), ami megmondja, hogy melyik pane van kiválasztva.
És készíts egy függvényt, ami ezt beállítja (pl. `setActivePane(x)`) és ami visszaadja, hogy egy adott pane van-e kiválasztva (pl. `isActive(pane)`).

Az Accordion `<script setup>`-jában "küldd le" az AccordionPane-eknek a vue `provide` függvényével a két függvényt egy objektumba becsomagolva, pl.

```
provide('accordionContext', { setActivePane, isActive })
```

Az AccordionPane setup-jában "fogadd" ezt az objektumot a vue `inject` függvényével, és használd fel őket.

</div>
