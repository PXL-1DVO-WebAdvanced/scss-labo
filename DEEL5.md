# Deel 5 - Navigatie
In het vijfde deel van het labo kan je verder bouwen op de code van deel 4.

Het grootste deel van de startpagina is klaar. Er mist echter nog een sectie om te navigeren. 
In deze opdracht bouw je daarom een navigatie die voor de helft vanuit de linkerzijde en voor de andere helft vanuit de rechterzijde van het scherm openklapt. 
Standaard gaat dit menu verborgen zijn.
Naast de navigatie voorzie je een “hamburgermenu” icoon, waarop geklikt kan worden om het navigatiemenu te openen. 
Dit icoon blijft tijdens het scrollen altijd zichtbaar en vormt een X wanneer er op geklikt wordt.
Het resultaat ziet er als volgt uit:

![navigatie](/assets/opgave/navmenu.png)
![navigatie](/assets/opgave/navitems.png)

## Git branch
- Doe een checkout van de main-/master-branch
- Synchroniseer je lokale repository met het *git pull* commando
- Controleer of de wijzigingen van deel4 zichtbaar zijn in de main-branch
- Maak een nieuwe branch aan in je repository: *memyselfandi/new/deel5*
- Doe een checkout van deze nieuwe branch

## Inhoud (html)
De HTML structuur voor de navigatie voorzien we bovenaan op de pagina, dus onder de openende body tag.
Voorzie hiervoor een nav element met de klasse ‘navbar’. Het openen van de navigatie gaan we laten gebeuren door een click-event op basis van een label en een checkbox. Voorzie binnen het nav element daarom het volgende:
- Een input element van het type checkbox, met de id ‘check’ en de klasse ‘checkbox’.
- Een div element dat de drie lijnen van het hamburgermenu gaat voorstellen, met de klasse ‘hamburger-menu’.
  - Voorzie binnen dit element een label element dat je linkt aan het eerder aangemaakte input element. Geef dit label de klasse ‘menu’.
    
    Binnen dit label maak je drie div elementen aan. Deze div elementen hebben allen de klasse ‘menu-line’ en hebben respectievelijk de volgende verschillende klasse:
    - ‘menu-line-1’
    - ‘menu-line-2’
    - ‘menu-line-3’
- Een div element dat de navigatie op zich gaat voorstellen met de klasse ‘navbar-navigation’.
  - Voorzie binnen dit element nog een div element met de klasse ‘navbar-navigation-left’. Dit element bevat drie img elementen met de gemeenschappelijke klasse ‘left-img’. Ze hebben elk een verschillend bronbestand en een verschillende klasse:
    - ‘nav-img-1.jpg’ – klasse: ‘left-img-1’
    - ‘nav-img-2.jpg’ – klasse: ‘left-img-2’
    - ‘nav-img-3.jpg’ – klasse: ‘left-img-3’
  - Voorzie nog een div element met de klasse ‘navbar-navigation-right’. Binnen dit element voorzie je een ongeordende lijst met klasse ‘nav-list’ en vijf lijstitems met de klasse ‘nav-list-item’.
    - Binnen een lijstitem voorzie je een anchor element dat linkt naar de huidige pagina, die de klasse ‘nav-list-link’ en respectievelijk de volgende tekst heeft:
      - Home
      - Products
      - Cart
      - About us
      - Contact
        
**Bekijk het resultaat in de browser**

## Opmaak
### Algemeen
#### _layout.scss
Door het toevoegen van deze extra HTML elementen, is de structuur van onze pagina hard gewijzigd.
We gaan daarom eerst en vooral de vormgeving van de afbeeldingen aanpassen. Selecteer daarom de afbeeldingen op basis van hun gemeenschappelijke klasse en geef ze een voorlopige breedte van 300px.

### navigatie
#### _layout.scss
Selecteer het element met de klasse ‘navbar’. Gebruik nesting om het element met de klasse ‘navbar-navigation’ aan te spreken en geef het als flex weer.

Gebruik nesting om het element met de klasse ‘navbar-navigation-left’ aan te spreken en geef het volgende eigenschappen:
-	Breedte: de helft van de breedte van het scherm
-	Hoogte: de volledige hoogte van het scherm
-	Achtergrondkleur: color-primary.

Spreek nu ook het element met de klasse ‘navbar-navigation-right’ op dezelfde manier aan en geef dit element dezelfde eigenschappen en waardes. Enkel voor de achtergrondkleur gebruik je color-secondary.

### left
#### _layout.scss
Verplaats de gemeenschappelijke klasse (‘left-img’) voor de afbeeldingen naar de selector voor de linkerzijde van het navigatiemenu.

Om de afbeeldingen op een bepaalde manier ten opzichte van elkaar te positioneren geef je ze een absolute positie geven. 
De parent klasse geef je geen relatieve maar wel een fixed positie (dit gaat ervoor zorgen dat dit element altijd op dezelfde plaats blijft staan ook al wordt er op de pagina gescrolled) en met de juiste eigenschap zorg je ervoor dat dit element helemaal links tegen het scherm komt te staan.

Aangezien we in de HTML structuur de navigatie eerst definiëren gaat dit door de positionering onder de andere elementen komen te liggen (het parallax effect). Geef daarom het element met de klasse ‘navbar’ een relatieve positie en een z-index van 200.

Wijzig de breedte van de afbeeldingen nu naar 50% om ze responsive te maken. Vervolgens gaan we iedere afbeelding apart positioneren:
-	Selecteer de eerste afbeelding op basis van de klasse en positioneer het op 2% van de bovenzijde en 2% van de linkerzijde.
-	Selecteer de tweede afbeelding op basis van de klasse en positioneer het op 3% van de onderzijde en 4% van de rechterzijde.
-	Selecteer de derde afbeelding op basis van de klasse en geef positioneer het op 30% van de bovenzijde en 25% van de linkerzijde.

Geef de afbeeldingen verder nog de volgende eigenschappen
-	een schaduweffect met de volgende waardes: ‘0 15px 60px rgba($color-black, .8)’
-	een opacity van 70%
-	afgeronde hoeken van 10px.

### right
#### _layout.scss
Geef het element voor de rechterzijde van de navigatie ook een fixed positie en zorg ervoor dat het element tegen de rechterkant van het scherm komt te staan.
De twee elementen binnen de navigatie komen nu in principe langs elkaar te staan.

Gebruik de mixin flexLayout om de navigatie-items te centreren in het midden van het element.

Selecteer vervolgens de klasse voor de ongeordende lijst. Spreek hierbinnen, door gebruik te maken van nesting, de lijstitems aan en haal de bullet-points weg.

Selecteer de anchor elementen op basis van de klasse en geef de elementen de volgende eigenschappen:
-	Lettertype: font-nunito
-	Lettergrootte: 80px
-	Laad de mixin textStyles in en geef het argument mee om de eerste letter als een hoofdletter weer te geven.
-	Tekstkleur: color-light
-	Haal de standaard stijl van het element af.
     
Een anchor element is een inline element waardoor je er standaard geen margin aan kan geven. Geef het element daarom weer als een block element, geef het een margin van 20px en centreer de tekst.

Zorg voor een hover effect waarbij de tekstkleur wijzigt naar ‘color-primary’ en de ruimte tussen de letters vergroot naar 4px. Zorg er met een transitie voor dat de overgang vertraagt wordt met een halve seconde.

## Hamburgermenu
### Verbergen
#### _layout.scss
Verberg het linker en het rechter deel van de navigatie. 
Geef respectievelijk de linker en rechterpositie een waarde -50vw. Hierdoor zal de header terug zichtbaar worden.

### Positionering
#### _components.scss
Selecteer het element voor het hamburgermenu op basis van haar klasse. Geef dit element voorlopig volgende eigenschappen:
-	Breedte: 40px
-	Hoogte: 40px
-	Achtergrondkleur: rood
     
Positioneer het element nu aan de rechterkant van het scherm met de volgende eigenschappen:
-	Fixed positie
-	7,5% van de bovenzijde
-	5% van de rechterkant

### Lijnen
#### _components.scss
Een hamburgermenu heeft drie horizontale lijnen. Deze zijn nu nog niet zichtbaar omdat de div elementen die we hiervoor hebben aangemaakt, geen content bevatten.

Selecteer het label element op basis van de klasse en laad in dit element de placeholder-selector fullSpace in.

Gebruik nesting om binnen dit element de elementen met de klasse ‘menu-line’ aan te spreken. Geef deze elementen de volgende eigenschappen:
-	Breedte: 100%
-	Hoogte: 4px
-	Achtergrondkleur: color-primary
     
De lijnen plakken nu nog tegen elkaar. Om dit op te lossen geef je het parent element een flex weergave, zet je de richting van de elementen op kolom en gebruik je voor de justify-content eigenschap de waarde space-around.

Verwijder tenslotte de rode achtergrondkleur op het hamburgermenu en geeft de cursor de waarde pointer.

## Functionaliteit
### Algemeen
#### _layout.css
Doordat het label gelinkt is aan de checkbox, kan je nu zien dat wanneer je op het hamburgermenu klikt, de checkbox van status gaat veranderen. Door deze mogelijkheid kunnen we enkel met CSS de klik functionaliteit in orde brengen.

Definieer wat er moet gebeuren wanneer de checkbox de status ‘checked’ heeft.
Selecteer hiervoor de checkbox op basis van de klasse en gebruik hierop de pseudo-klasse ‘checked’. 
Hierbinnen kunnen we dan eigenschappen definiëren die enkel van toepassing zijn wanneer de checkbox aangevinkt is.

### Onderdelen
#### _layout.scss & _components.scss
Het linker- en rechterdeel van het navigatiemenu moeten tevoorschijn komen wanneer je klikt op het hamburgermenu.

Om die aan te spreken gebruiken we de ‘general sibling combinator’ (een onderdeel dat standaard ook in CSS beschikbaar is: https://developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_combinator).

De selector voor het linker deel ziet er dan als volgt uit:
‘.checkbox:checked ~ .navbar-navigation .navbar-navigation-left {}‘
Zorg er dan voor dat de linker positie van het element de waarde 0 krijgt.

Doe hetzelfde voor het rechter deel, maar geef dan de rechter positie van het element de waarde 0.

Het linker en rechterdeel zullen nu tevoorschijn komen. Je zal echter merken dat het icoon van het hamburgermenu verdwenen is. We kunnen dit oplossen door de z-index hoger te zetten dan de z-index van het navigatiemenu. Geef het element met de klasse ‘hamburger-menu’ dus een z-index van bijvoorbeeld 250.

De overgang gebeurt nu nogal abrupt. Daarom gaan we transities toevoegen:
-	Aan het linkerdeel geef je een transitie op de left eigenschap van 0,8s. Je kan ook nog een extra effect toevoegen door aan de transition eigenschap de ‘cubic-bezier’ functie toe te voegen: cubic-bezier(1, 0, 0, 1).
-	Doe voor het rechterdeel hetzelfde, maar dan op de right eigenschap.

### Icoon
#### _layout.scss & _components.scss
Tenslotte gaan we het hamburgermenu icoon bij een klik omzetten naar een ‘X’. Dit moet dus opnieuw gebeuren wanneer de checkbox checked is. Gebruik daarom de juiste selector en roteer het icoon ten opzichte van de z-as. Gebruik hiervoor volgende eigenschap:
-	transform: rotate(90deg)

Op het element met de klasse ‘menu’ voeg je ook een transitie toe op de transform van 0,5s.

Op dit moment zullen de lijnen verticaal komen te staan. Om er een kruis van te maken, verberg je de middelste lijn. De bovenste lijn draai je 40° in negatieve zin en de onderste lijn draai je 40° in de positieve zin.
Zorg vervolgens voor een transitie op het element met de klasse ‘menu-line’ voor alle eigenschappen met een duur van 0,5s én een vertraging van 0,5s.

Hierdoor krijg je nog geen kruis. Dit komt omdat de lijnen worden gedraaid ten opzichte van het midden van het element. Voeg daarom ook de eigenschap ‘transform-origin’ toe en geef het de waarde ‘right’.

Verberg uiteindelijk nog de checkbox. Dit kan je doen door met een CSS eigenschap, maar ook door het ‘hidden’ attribuut toe te voegen aan het HTML element.


## Resultaat
**Bekijk het resultaat in de browser!**

## Git branch
Wanneer je 100% tevreden bent over het resultaat doe je een commit en push van je branch *memyselfandi/new/deel4*. Gebruik als commit-message: *deel4 - footer*

Ga vervolgens naar je repository op github.com om een merge te doen van deze branch met je main-/master-branch.

