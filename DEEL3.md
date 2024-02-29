# Deel 3 - Producten in de kijker
In het derde deel van het labo kan je verder bouwen op de code van deel 2.

Onder de about sectie die je in het vorige labo hebt gemaakt, voorzie je een sectie waar producten in de kijker kunnen getoond worden. Deze sectie ziet er als volgt uitziet (het eerste product wordt in de hover state getoond):

![about](/assets/opgave/producten.png)

## Git branch
- Doe een checkout van de main-/master-branch
- Synchroniseer je lokale repository met het *git pull* commando
- Controleer of de wijzigingen van deel2 zichtbaar zijn in de main-branch
- Maak een nieuwe branch aan in je repository: *memyselfandi/new/deel3*

## Inhoud (html)
Voorzie onder de ‘about’ sectie in het index.html bestand de volgende structuur:
- Een section element met de klasse ‘gallery‘ met hierbinnen:
  - Een div element met de klasse ‘cards-wrapper’ waarbinnen zes elementen met dezelfde structuur worden aangemaakt, maar wel andere content wordt gebruikt. Een element heeft de volgende structuur:
    - Een div element met de klasse ‘card’. Voorzie binnen deze div de volgende elementen:
      - Een div element met de klasse ‘card-overlay’ waarbinnen volgende elementen worden aangemaakt:
        - Een heading van niveau 1 met de klasse ‘card-overlay-heading’ met de tekst ‘Yeezy Boost 700 – Hi-Res Blue’.
        - Een paragraaf met de klasse ‘card-overlay-paragraph’ met de tekst ‘Price: €300’.
        - Een button van het type ‘button’ met de klasse ‘card-overlay-button’ en de tekst ‘Order now’.
        - Een img element met de klasse ‘card-image’ met een pad naar de afbeelding ‘gallery_1.jpg’. (Opgelet het pad start in dit geval vanuit het HTML bestand.)

Voor de content van de andere vijf elementen kan je volgende data gebruiken:
-	‘Air Jordan 4 Retro SE – Black Canvas’ – ‘Price:€280’ - ‘gallery_2.jpg’
-	‘Wtaps X Authentic Syndicate - Wings’ – ‘Price:€125’ - ‘gallery_3.jpg’
-	‘Undefeated X Zoom Kobe 1 ProTro – White Gum’ – ‘Price:€625’ - ‘gallery_4.jpg’
-	‘Air Jordan 4 Retro – Red Thunder’ – ‘Price:€360’ - ‘gallery_5.jpg’
-	‘Off-White X Air Force 1 Low - Brooklyn’ – ‘Price:€1325’ - ‘gallery_6.jpg’


**Bekijk het resultaat in de browser**

## Opmaak
### Algemeen
#### _layout.scss
Selecteer het section element op basis van haar klasse.

Selecteer, door gebruik te maken van nesting, het element met de klasse ‘cards-wrapper’ en zorg voor een flex weergave.
Geef dit element ook een witte achtergrondkleur. Maak hiervoor een nieuwe variabele aan ‘color-white’ en geef deze de waarde ‘#fff’.
Op deze manier staan alle cards langs elkaar in één rij. We gaan nu een card zelf verder vormgeven.

### card
#### _components.scss & _layout.scss
Selecteer een card op basis van zijn klasse. We gaan drie cards per rij weergeven, dus definieer een breedte van 33.3333%.

De cards staan nu nog op 1 rij. Voorzie daarom volgende eigenschap in het element met de klasse ‘cards-wrapper’: flex-wrap: wrap. Op die manier creëren we twee rijen met 3 cards.

Geef een card nu een hoogte van 30vw. Hiermee maken we ze responsive omdat ze elk ongeveer 30% van de viewport innemen.

### card-overlay
#### _components.scss
Gebruik nesting om het element met de klasse ‘card-overlay’ aan te spreken.
Geef het element een absolute positie. Om de positie nu te definiëren ten opzichte van een card geven we het parent element een relatieve positie.

Positioneer het element nu ten opzichte van de boven- en linkerzijde met een waarde 0. Zorg ook voor een breedte en hoogte van 100%.

Gebruik de rgba functie van Sass om de achtergrondkleur te wijzigen. Geef deze functie de ‘color-primary’ als kleur en 50% als waarde voor de opacity mee.
Pas de tekstkleur aan naar ‘color-white’.

Geef het element ook een z-index van 10, zodat dit bovenop het andere element komt te liggen.

Laad de ‘flexLayout’ mixin in om de elementen te centreren. De elementen komen nu in een rij te staan. Zorg ervoor dat de elementen onder elkaar komen te staan.

### titel
#### _components.scss & _base.scss
Gebruik nesting om de heading binnen het element met klasse ‘card-overlay’ te selecteren. Geef dit element de volgende eigenschappen:
-	Lettertype: font-nunito
-	Lettergrootte: 50px
-	Centreer de tekst

We kunnen nu de mixin textStyles gebruiken om de tekst verder vorm te geven. 
De tekst zou enkel niet volledig in hoofdletters moeten getoond worden, maar enkel de eerste letter van de tekst. 
Geef de mixin daarom een default parameter ‘transform’ die standaard de waarde uppercase krijgt. 
Pas de parameter toe binnen de mixin en gebruik de mixin vervolgens in het element en geef het argument mee om enkel de eerste letter als een hoofdletter weer te geven.

### paragraaf
#### _components.scss
Gebruik nesting om de paragraaf binnen het element met klasse ‘card-overlay’ te selecteren.
Geef dit element de volgende eigenschappen:
-	Lettertype: font-josefinSans
-	Lettergrootte: 30px
-	Onderste margin van 30px
-	De mixin textStyles met als argument de waarde om de eerste letter als een hoofdletter weer te geven.

### button
#### _components.scss
Gebruik nesting om de knop binnen het element met klasse ‘card-overlay’ te selecteren.
Geef dit element de volgende eigenschappen:
-	Breedte van 150px
-	Hoogte van 40px
-	Tekstkleur: color-primary
-	Achtergrondkleur: color-white
-	Lettertype: font-josefinSans
-	Lettergrootte: 14px
-	Vetgedrukt
-	Hoofdletters
-	Ruimte van 1px tussen de letters.
-	Een border van 1px, solid met color-primary
-	Een afronding van 30px voor de border
-	Geen outline
-	Als cursor de pointer.

### card-overlay hover
#### _components.scss
We gaan de overlay van de linkerzijde van de card laten vertrekken. Hiervoor gaan we het volgende doen:
- Zorg ervoor dat de overlay standaard niet zichtbaar door het volgende toe te passen:
  - Zet de linker positie van de overlay op -100%
  - Geef het element met de klasse ‘card’ een verborgen overflow.
- Voeg een hover effect toe op het element met de klasse ‘card’ en spreek hierbij de klasse ‘card-overlay’ aan. (het hover effect kan niet rechtstreeks op de klasse (of het element) worden gezet, omdat deze standaard niet zichtbaar zijn en er dus ook niet over gehovered kan worden). En wijzig volgende elementen:
  - Linker positie: 0
- Zet een transitie op de linker positie eigenschap van de overlay met een vertraging van .7s.

### afbeelding
#### _components.scss & _base.scss
Gebruik nesting om het element met de klasse ‘card-image’ aan te spreken.
Geef het element een breedte en een hoogte van 100%. Hierdoor zullen de afbeeldingen er gestretcht uitzien. Gebruik de object-fit eigenschap met de waarde ‘contain’ om dit op te lossen. Geef de afbeelding een padding van 5px.

We gebruiken nu in de afbeelding en de overlay telkens een breedte en hoogte van 100%. Maak hiervoor een placeholder-selector ‘fullSpace’ in het _base.scss bestand en doe aan overerving in beide selectoren.

## Resultaat
**Bekijk het resultaat in de browser!**

## Git branch
Wanneer je 100% tevreden bent over het resultaat doe je een commit en push van je branch *memyselfandi/new/deel3*. Gebruik als commit-message: *deel3 - producten*

Ga vervolgens naar je repository op github.com om een merge te doen van deze branch met je main-/master-branch.
