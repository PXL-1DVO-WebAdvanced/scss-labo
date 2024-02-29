# Deel 1 - Header
In dit eerste deel bouw je de header van de webpagina op.

![header](/assets/opgave/header.png)

Met hover effect: 
![header-hover](/assets/opgave/header-hover.png)

## Git branch
- Maak een nieuwe branch aan in je repository: *memyselfandi/new/deel1*
- Doe een checkout van deze nieuwe branch

## Structuur scss-bestanden
Tijdens de opbouw van de cursus hebben we hoofdzakelijk gewerkt met een main.scss bestand.
We gaan de code in dit labo opsplitsen in verschillende bestanden.
Maak daarom volgende partials aan in de scss map:
- _base.scss: hierin komen alle variabelen, mixins, ….
- _components.scss: hierin komt de stijl voor herbruikbare elementen zoals bijvoorbeeld buttons.
- _layout.scss: hier gaan we de effectieve styling in onder brengen.

Laad deze bestanden in het main.scss bestand (tip: @use).

## Inhoud (html)
Voor de header bouwen we de volgende structuur in het index.html bestand (binnen het body element):
- Een header element met de klasse ‘header’.
    - Binnen het header-element maken we een div element aan met de klasse ‘brand’.
        - Maak binnen deze div eerst een anchor element aan dat linkt naar de huidige pagina en de klasse ‘logo’ heeft.
            - Binnen het anchor-element maak je een icon element aan die je de klasse ‘fas fa-shoe-prints’ (klasse om een fontawesome icon te genereren) geeft.
        - Maak vervolgens binnen deze div nog een div element aan met volgende elementen:
            - Een heading van niveau 1 aan met de klasse ‘main-name’ en de tekst ‘Snaky Sneakers’.
            - Een paragraaf met de klasse ‘sub-name’ en de tekst ‘Sneaker Reseller’.
- Maak binnen het header-element nog een div element aan met de klasse ‘header-banner’. Maak binnen dit element volgende elementen aan:
    - Een heading van niveau 1 met als klasse ‘main-heading’ en de tekst ‘Welcome’.
    - Een heading van niveau 3 met als klasse ‘sub-heading’ en de tekst ‘Find your preferred sneakers now’.
    - Een button van het type ‘button’, met de klasse ‘main-button’ en de tekst ‘Buy now’

**Bekijk het resultaat in de browser**

## Opmaak
### Algemeen
#### _base.scss
We zorgen er eerst voor dat de standaard margin en padding van alle elementen wordt gereset.
- Geef de selector ‘*’ (dat staat voor alle HTML-elementen) een margin en een padding van 0.
- Zorg ervoor dat de randen en de witruimtes binnen de elementen worden meegerekend in de eventuele ingestelde breedtes van de HTML-elementen.
- Vervolgens geven we de body een andere achtergrondkleur. Maak voor de kleur een variabele ‘color-light’ aan en geef deze de hex-waarde ‘#f9f9f9’.

### header
#### _layout.scss
Laad _base.scss in zodat alle variabelen kunnen gebruikt worden:

    @use ‘base’ as *

Spreek het header-element aan op basis van haar klasse.
- Het element neemt de volledige breedte van het scherm in en de volledige hoogte van de viewport (tip: 100vh).
- Zorg voor een achtergrondafbeelding voor het element en gebruik hiervoor de afbeelding ‘bg.jpg’. Dit kan je op volgende manier aanpakken met de eigenschappen:
    - background: (zie ‘linear gradient’ hieronder)
    - background-position: center
    - background-repeat: no-repeat
    - background-size: cover

Voorzie ook een ‘linear gradient’ van 60% naar 40% op de afbeelding.
Voor het definiëren van deze gradiënt gebruiken we de rgba-functie van Sass.
We gaan hiervoor de kleur ‘#000’ gebruiken, dus definieer deze eerst in het _base.scss bestand als ‘color-black’.
De eigenschap voor de achtergrond krijgt uiteindelijk volgende waarde:

    linear-gradient(rgba($color-black, .6), rgba($color-black, .4)), url(<pad naar het bestand>)’

Opgelet: indien de afbeelding niet wordt weergegeven is het pad niet juist gedefinieerd. Aangezien je dit pad opgeeft in de scss, die nadien gecompileerd wordt naar het main.css bestand, ga je het pad relatief vanuit dat bestand moeten definiëren.

### brand
#### _layout.scss
Gebruik het principe van nesting om de ‘brand’ klasse binnen de ‘header’ klasse aan te spreken.
We willen nu het logo centraal positioneren. Geef het element daarom een absolute positie, laat het 15% zakken van de bovenzijde en zet het in het midden (50%) ten opzichte van de linkerzijde.
Om het element zelf helemaal in het midden te zetten gebruiken we de transform eigenschap en geven we deze de waarde:

    transform: translate(-50%, -50%);

Aangezien we dit element een absolute positie geven, moeten we het parent element (header) nog een relatieve positie geven.
Geef de tekstkleur de waarde ‘#262626’, gebruik hiervoor de variabele ‘color-dark’ die je aanmaakt in het _base.scss bestand.

### logo
Nu het element gecentreerd is, gaan we de elementen erbinnen vormgeven. We gaan het logo nog op een andere plaats binnen de website gebruiken. Daarom gaan we de stijl binnen _components.scss plaatsen. Laad hierin eerst _base.scss in zodat alle variabelen kunnen gebruikt worden.
Spreek het anchor element rond het logo aan op basis van haar klasse. Geef het een lettergrootte van 70px. Geef de tekst een kleur, definieer hiervoor een nieuwe kleur in _base.scss: ‘color-primary’ en geef deze de waarde ‘#003459’. Zet de text-decoration eigenschap nu op ‘none’.
Een anchor element is een inline element waardoor we het standaard geen breedte en hoogte kunnen geven. Geef het daarom weer als een ‘block’ element en geef het element een hoogte en een breedte van 110px.

### teksten logo
Binnen het element met klasse ‘brand’ gaan we de teksten en het logo langs elkaar plaatsen. Geef het element daarom weer als ‘flex’ en centreer de items verticaal en horizontaal.
Deze flexbox eigenschappen gaan we nog meermaals nodig hebben. Maak daarom een mixin ‘flexLayout’ aan in _base.scss, zet de eigenschappen hierin en vervang deze eigenschappen in de klasse ‘brand’ met de mixin. Laad de mixin ook in de klasse logo in.

Aangezien we meerdere lettertypes gaan gebruiken, definiëren we eerst drie nieuwe variabelen in _base.scss:
-	font-dancingScript: ‘Dancing Script’, cursive
-	font-josefinSans: ‘Josefin Sans’, sans-serif
-	font-nunito: ‘Nunito’, sans-serif

Het element met de klasse ‘main-name’ geven we nu de volgende stijl (het is een specifiek component, dus gebruiken we _components.scss):
-	lettertype: $font-nunito
-	lettergrootte: 50px
-	Maak voor de kleur een nieuwe variabele ‘color-secondary’ aan en geef deze de waarde ‘#bbb’.

Om dit element nu verder vorm te geven maken we nog een mixin aan met de naam ‘textStyles’ en laden we deze in de klasse ‘main-name’ in. Deze krijgt volgende waardes:
-	font-weight: 300
-	letter-spacing: 2px
-	de tekst dient weergegeven te worden in hoofdletters.
-	centreer de tekst in het midden.

Het element met de klasse ‘sub-name’ stijlen we op de volgende manier:
-	lettertype: $font-josefineSans
-	lettergrootte: 18px
-	tekstkleur: $color-secondary
-	de mixin textStyles

### afwerking
Het logo en de teksten staan nu te kort op elkaar. We geven het element met klasse ‘logo’ daarom een rechter margin van 20px.
Haal ook de tekstkleur van het element met klasse ‘brand’ af. We hebben in de vorige stap namelijk een kleur voor alle child elementen voorzien.

**Bekijk het resultaat in de browser!**

## Vervolg

### header-banner
#### _layout.scss
Gebruik nesting om de ‘header-banner’ klasse binnen de ‘header’ klasse aan te spreken. (Hiervoor kan je ipv ‘header-banner’ ook ‘&-banner’ gebruiken.)
Centreer het element nu mooi in het midden van de viewport. Hiervoor gaan we een aantal identieke eigenschappen gebruiken als in de ‘brand’ klasse. 
Maak daarom een nieuwe mixin aan van de eigenschappen position, top, left en transform. Enkel voor top gaan we ipv 15%, 50% nodig hebben. Zorg daarom voor een ‘$topValue’ parameter voor de mixin.
Laad deze vervolgens in de ‘brand’ en ‘header-banner’ klasse in met de respectievelijke juiste waarde voor de top eigenschap.

Centreer met een text-align eigenschap nu de elementen in het midden van het ‘header-banner’ element.

### main-heading
#### _components.scss
Pas hierop volgende eigenschappen toe:
-	lettertype: $font-dancingScript
-	lettergrootte: 100px
-	font-weight: 300
-	tekstkleur: $color-primary
-	onderste margin van 40px

### sub-heading
#### _components.scss
Pas vervolgens volgende eigenschappen toe:
-	lettertype: $font-josefinSans
-	lettergrootte: 60px
-	font-weight: 300
-	tekstkleur: $color-secondary
-	onderste margin van 80px

### button
#### _components.scss
-	Geef het element een breedte van 170px en een hoogte van 45px.
-	Gebruik de $font-josefinSans variabele voor het lettertype.
-	Lettergrootte: 14px
-	Zorg dat de letters in hoofdletters staan.
-	Zorg voor een ruimte tussen de letters van 1px.
-	Tekstkleur: $color-primary
-	Maak de achtergrondkleur transparant
-	Geef het element een rand van 1px, solid en gebruik de variabele $color-primary voor de kleur.
-	Zorg ervoor dat er geen outline is
-	Zet de cursor op ‘pointer’.

Creëer een hover effect voor dit element. Bij een hover:
-	Wijzigt de kleur van de achtergrond naar $color-primary
-	Wijzigt de tekstkleur naar $color-secondary

Zorg tenslotte voor een transition eigenschap met de waardes ‘all .4s’

## Resultaat
**Bekijk het resultaat in de browser!**

## Git branch
Wanneer je 100% tevreden bent over het resultaat doe je een commit en push van je branch *memyselfandi/new/deel1*. Gebruik als commit-message: *deel1 - header*

Ga vervolgens naar je repository op github.com om een merge te doen van deze branch met je main-/master-branch.

## Next!
[Ga naar deel 2](DEEL2.md)