# Deel 2 - About
In het tweede deel van het labo kan je verder bouwen op de code van het vorige labo.
Onder de header die je in het vorige labo hebt gemaakt, voorzie je een about sectie die er als volgt uit ziet:

![about](/assets/opgave/about.png)
![about-hover](/assets/opgave/about-hover.png)

## Git branch
- Doe een checkout van de main-/master-branch
- Synchroniseer je lokale repository met het *git pull* commando
- Controleer of de wijzigingen van deel1 zichtbaar zijn in de main-branch
- Maak een nieuwe branch aan in je repository: *memyselfandi/new/deel2*
- Doe een checkout van deze nieuwe branch

## Inhoud (html)
Voorzie onder het header-element in het index.html bestand de volgende structuur:
- Een section element met de klasse ‘about’ met hierbinnen:
  - Een div element met de klasse ‘about-left’. 
    - Voorzie in deze div een img element en gebruik het ‘team.jpg’ bestand als bron.
  - Een div element met de klasse ‘about-right’. Voorzie hierbinnen volgende elementen:
    - Een heading van niveau 1 met als klasse ‘main-heading’ en de tekst ‘Our team’.
    - Een heading van niveau 3 met als klasse ‘sub-heading’ en de tekst ‘Only for the best sneaker experience’.
    (Opmerking: dit zijn elementen die we ook in de heading hebben gebruikt én waarvoor we dus ook al de stijl hebben voorzien)
    - Een div element met de klasse ‘stars’. Voorzie binnen dit element drie keer volgend element:
    - Een icon element met de klassen ‘fas fa-star-of-life star’.
    - Een paragraaf met de klasse ‘description’. Hierin voorzien we dummy tekst (deze tekst kan je bijvoorbeeld genereren door ‘lorem50’ te typen en dan op de tab-toets te drukken.)
    - Een kopie van het div-element met de klasse ‘stars’.
    - Een button van het type ‘button’ met de klasse ‘main-button’ en de tekst ‘Read more’. (Ook dit is een kopie van een eerder aangemaakt element.)

**Bekijk het resultaat in de browser**

## Opmaak
### Algemeen
#### _layout.scss
Selecteer het section element op basis van haar klasse.
Voorzie een hoogte van 90% van de viewport. 

Om er voor te zorgen dat de interne div elementen naast elkaar komen te staan geven we het element weer als flex en centreren we de items verticaal.

### about-left
Gebruik nesting om het div linker element op basis van haar klasse aan te spreken binnen het section element.
Geef het element een breedte van 40%.
Spreek binnen dit element de afbeelding aan en geef deze een breedte van 100%. Op die manier maken we de afbeelding responsive en neemt deze 100% van de breedte in van het parent element (dat 40% van de breedte inneemt).

We gaan nu maar een gedeelte van de afbeelding laten zien. Geef daarom het div element een relatieve positie en geef het een negatieve linker margin van 150px;

Om de stijl van de afbeeldingen door te trekken geven we de afbeelding een opacitiy van 70%.

### about-right
Spreek nu ook het rechter div-element aan op basis van haar klasse en gebruik hier ook nesting voor.
Laat het element de rest van de breedte innemen (60%).
Geef het element weer als flex en zorg ervoor dat de elementen onder elkaar ipv naast elkaar worden weergegeven (tip: flex-direction) en verticaal worden gecentreerd.

Vervolgens gaan we de sterren vormgeven. Selecteer daarom binnen dit rechter div element de elementen met de klasse ‘stars’ en geef deze elementen een bovenste en onderste margin van 30px.

Selecteer nu de individuele sterren op basis van de klasse ‘star’. Geef ze een lettergrootte van 15px, gebruik als tekstkleur de ‘color-primary’. Zorg ervoor dat de elementen, buiten het eerste element, een linker margin van 10px krijgen.

Selecteer de paragraaf op basis van de klasse en geef het de volgende stijl:
-	Lettertype: ‘font-josefineSans’
-	Lettergrootte: 25px
-	Schuingedrukt
-	Tekstkleur: ‘color-secondary’
-	Aligneer de tekst met de ‘justify’ waarde.

Wanneer je de pagina nu bekijkt zal je zien dat de tekst van het scherm verdwijnt. 
Om dit te vermijden passen we op het parent div-element linker en rechter padding toe van 100px. 

Tenslotte gaan we een witruimte voorzien aan het begin van de paragraaf. Voorzie daarom de pseudo-klasse ‘first-letter’ op het paragraaf element en zorg voor een linker padding van 50px.

### afwerking
We hebben een heading met daaronder een section element aangemaakt. Je zal nu zien dat er een scrollbar getoond wordt op het scherm in de browser.
Om deze te verbergen gaan we de volgende code toevoegen aan _base.scss.
Spreek de -webkit-scrollbar klasse aan op het body element en zet de weergave op none.

Spreek ook het html element aan en zet de eigenschap scrollbar-width op none

## Resultaat
**Bekijk het resultaat in de browser!**

## Git branch
Wanneer je 100% tevreden bent over het resultaat doe je een commit en push van je branch *memyselfandi/new/deel2*. Gebruik als commit-message: *deel2 - about*

Ga vervolgens naar je repository op github.com om een merge te doen van deze branch met je main-/master-branch.

## Next!
[Ga naar deel 3](DEEL3.md)