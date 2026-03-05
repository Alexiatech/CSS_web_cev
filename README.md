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

