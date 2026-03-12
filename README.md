# CSS_web_cev

## Wat heb ik vandaag gedaan?
De hele dag ben ik bezig geweest met het onderzoeken en toepassen van CSS filters en masks.  
Ik heb verschillende artikelen en voorbeelden bestudeerd en deze kennis vervolgens toegepast in de oefeningen en mijn website.

Het doel was om beter te begrijpen hoe visuele effecten werken in CSS en hoe je deze kunt inzetten om een ontwerp interessanter en dynamischer te maken.

---

## Gekozen onderwerpen

### Filters
CSS filters maken het mogelijk om visuele effecten toe te passen op elementen, zoals blur, brightness, contrast en grayscale.  
Hiermee kun je snel sfeer en nadruk toevoegen aan afbeeldingen of UI-elementen zonder extra grafische assets te gebruiken.

Ik heb geëxperimenteerd met:
- `blur()`
- `brightness()`
- `contrast()`
- Het combineren (chainen) van meerdere filters

---

### Masks
Met CSS masks kun je delen van een element zichtbaar of onzichtbaar maken.  
Dit geeft veel creatieve controle over vormen, patronen en overlays.

Ik heb geoefend met:
- Basis mask properties
- Combineren van masks met afbeeldingen
- Het gebruiken van masks voor creatieve visuele effecten

- ## Wat ik vandaag heb gedaan

- Begonnen met de presentatie waar we gisteren aan hebben gewerkt. Hierbij heb ik verschillende CSS-functies geleerd en toegepast.
- Deelgenomen aan de kickstart van de CSS, waarin werd uitgelegd wat er van ons verwacht wordt.
- Onderzoek gedaan naar wat ik kan maken en wat ik leuk vind om te ontwikkelen.
- Een eerste snelle template gemaakt van wat ik verwacht te gaan maken.

## Weekly Nerd – Peter Paul Koch (Browsers)

Tijdens de Weekly Nerd kwam Peter Paul Koch langs en vertelde hij over hoe browsers werken en hoe ze door de jaren heen zijn ontwikkeld. Ik heb tijdens het college tekeningen gemaakt om het beter te begrijpen.

### Wat doet een browser?
Een browser haalt de code op van een website: HTML, CSS en JavaScript.  
- HTML is de markup en bepaalt de structuur van de pagina.  
- CSS zorgt voor de styling.  
- JavaScript zorgt voor interactie.  

Vanuit de HTML wordt de DOM (Document Object Model) gemaakt. Dit is een model van de HTML dat JavaScript kan gebruiken om onderdelen van de pagina aan te passen. Daarnaast bestaat er ook de AOM (Accessibility Object Model), die lijkt op de DOM maar gericht is op toegankelijkheid en specifieke interface-instructies.

### Parsing en rendering
Een parser leest de HTML als tekst en vertaalt dit naar instructies die de browser begrijpt. De JavaScript engine voert de scripts uit, maar is niet verantwoordelijk voor het parsen en renderen van HTML en CSS of voor het bouwen van de DOM; dat doet de browser zelf.

We hebben ook geleerd dat CSS en layout het zwaarste zijn voor de browser om te berekenen. JavaScript kan het renderen blokkeren, behalve wanneer je `async` of `defer` gebruikt.

### Core vs DOM
- Core: de JavaScript programmeertaal zelf.  
- DOM: de manier waarop JavaScript de HTML-pagina kan aanspreken en aanpassen.

### Backward compatibility
Browsers moeten alles wat ze ooit hebben ondersteund blijven ondersteunen. Daarom werken oude dingen zoals:
```html 
<body bgcolor="abdaca">
<frameset>
```


# Dag 2 – Ideeontwikkeling

Vandaag ben ik verder gegaan met het bedenken van een concept voor mijn CSS project.

Ik wilde iets maken dat zowel interactief als visueel interessant is. Uiteindelijk kwam ik op het idee om een **Tamagotchi-achtig apparaat** te maken dat volledig met CSS werkt.

Het idee was dat de gebruiker via knoppen verschillende emoties van het karakter kan activeren.

Ik heb onderzocht:

- Hoe interactieve states werken in CSS
- Hoe ik zonder JavaScript toch interactie kan maken
- Hoe CSS selectors zoals `:checked` en `:has()` werken

### Eerste experiment

```css
input[type="radio"]:checked {
  background: red;
}
```

## Dag 3 – Pixel art maken met CSS

Vandaag ben ik verder gegaan met het bouwen van het scherm van mijn Tamagotchi.  
Mijn doel was om een karakter te maken zonder afbeeldingen, zodat alles volledig met CSS gemaakt wordt.

Ik heb hiervoor een techniek gebruikt waarbij **box-shadow wordt gebruikt om pixels te tekenen**. Door meerdere shadows te plaatsen op verschillende posities kun je een pixelachtig patroon maken.

Voorbeeld van de code die ik hiervoor heb gebruikt:

```css
section div::before {
  box-shadow:
    calc(4 * var(--p)) calc(3 * var(--p)) black,
    calc(4 * var(--p)) calc(2 * var(--p)) black,
    calc(8 * var(--p)) calc(3 * var(--p)) black,
    calc(8 * var(--p)) calc(2 * var(--p)) black;
}
```

# Dag 4 – Animaties en emoties voor het karakter

Vandaag heb ik verder gewerkt aan de emoties van mijn Tamagotchi karakter. Het doel was dat elke knop een andere emotie of reactie laat zien op het scherm.

Om dit te bereiken heb ik gebruik gemaakt van **CSS keyframe animaties**. Met keyframes kun je een animatie maken door een begin- en eindstaat te definiëren.

Een voorbeeld hiervan is de animatie voor een verdrietige emotie:

```css
@keyframes --sad {
  100% {
    box-shadow:
      calc(4 * var(--p)) calc(3 * var(--p)) black,
      calc(4 * var(--p)) calc(2 * var(--p)) black,
      calc(8 * var(--p)) calc(3 * var(--p)) black,
      calc(8 * var(--p)) calc(2 * var(--p)) black,
      calc(3 * var(--p)) calc(12 * var(--p)) black,
      calc(4 * var(--p)) calc(11 * var(--p)) black,
      calc(5 * var(--p)) calc(10 * var(--p)) black,
      calc(6 * var(--p)) calc(10 * var(--p)) black,
      calc(7 * var(--p)) calc(10 * var(--p)) black,
      calc(8 * var(--p)) calc(11 * var(--p)) black,
      calc(9 * var(--p)) calc(12 * var(--p)) black;
  }
}
```

Ik gebruik hier opnieuw de **box-shadow pixel techniek**. Door de positie van de pixels te veranderen kan ik bijvoorbeeld de mond van het karakter aanpassen zodat deze verdrietig of boos kijkt.

De animatie wordt geactiveerd via een radio button:

```css
section input:nth-child(1)[type="radio"]:checked ~ section div::before {
  animation-name: --sad;
  animation-duration: 1s;
  animation-fill-mode: forwards;
}
```

Hier gebruik ik de **`:checked` selector**. Deze selector wordt actief wanneer een input geselecteerd wordt.

Daarnaast gebruik ik de **general sibling selector (`~`)**. Hierdoor kan een element dat later in de HTML staat aangepast worden wanneer een knop geselecteerd is.

Ik heb deze techniek gebruikt omdat ik geen **JavaScript** mocht gebruiken, maar toch interactie wilde maken.

---

# Dag 5 – Power knop en interactie logica

Vandaag heb ik een **power knop** toegevoegd aan mijn interface.

De power knop bepaalt of het scherm actief is of niet. Ik heb hiervoor een **checkbox** gebruikt omdat een checkbox twee states heeft:

* `checked`
* `unchecked`

Om te controleren of de power knop aan staat heb ik de **CSS selector `:has()`** gebruikt.

```css
body:has(header input:checked)
```

Deze selector kijkt of er een checkbox actief is binnen de header.

Hiermee kon ik logica maken:

* Power uit → scherm uit
* Power aan → animaties zichtbaar

Daarnaast heb ik de power knop een stijl gegeven zodat deze lijkt op een **arcade knop**.

```css
input[type="checkbox"]{
  appearance: none;
  width: 60px;
  height: 60px;
  background: #d62828;
  border-radius: 50%;
  border: 6px solid #7a0d0d;

  box-shadow:
    inset 0 -6px 0 #7a0d0d,
    0 4px 0 #3d0707;
}
```

Ik gebruik `appearance: none` omdat browsers standaard styling geven aan inputs. Door dit uit te zetten kan ik de knop volledig zelf ontwerpen.

De combinatie van schaduwen zorgt voor een **3D effect**, waardoor het lijkt alsof de knop uit het apparaat steekt.

Wanneer de knop wordt ingedrukt:

```css
input[type="checkbox"]:active{
  transform: translateY(3px);
}
```

Hierdoor lijkt het alsof de knop fysiek wordt ingedrukt.

---

# Dag 6 – Easter eggs en responsive design

Vandaag heb ik extra interacties toegevoegd aan mijn project.

## Confetti animatie

Ik heb een **easter egg** gemaakt waarbij confetti verschijnt wanneer een specifieke knop wordt geselecteerd.

```css
@keyframes --confettiFall {
  0% {
    box-shadow:
      calc(1 * var(--p)) calc(0 * var(--p)) red,
      calc(4 * var(--p)) calc(1 * var(--p)) yellow,
      calc(7 * var(--p)) calc(0 * var(--p)) blue;
  }

  100% {
    box-shadow:
      calc(1 * var(--p)) calc(8 * var(--p)) red,
      calc(4 * var(--p)) calc(9 * var(--p)) yellow,
      calc(7 * var(--p)) calc(8 * var(--p)) blue;
  }
}
```

Door de **Y-positie van de pixels te veranderen** lijkt het alsof de confetti naar beneden valt.

De animatie wordt alleen geactiveerd wanneer twee voorwaarden waar zijn:

* De power knop staat aan
* De vierde radio button is geselecteerd

---

## Responsive design

Omdat mijn interface ook op **mobiele schermen** moet werken heb ik een media query toegevoegd.

```css
@media (max-width:700px){

  section div{
    --p: 12px;
  }

}
```

Omdat alle pixelposities gebaseerd zijn op de variabele `--p`, schaalt het hele pixel gezicht automatisch mee wanneer ik deze waarde verander.

Dit was een efficiënte oplossing omdat ik niet alle `box-shadow` waarden opnieuw hoefde te schrijven.


