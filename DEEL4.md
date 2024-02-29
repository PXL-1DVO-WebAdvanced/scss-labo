# Deel 4 - Footer
In het vierde deel van het labo kan je verder bouwen op de code van deel 3.

Het doel van deze opdracht is om de footer uit te werken en vorm te geven. Het resultaat moet er als volgt gaan uitzien:

![footer](/assets/opgave/footer.png)

## Git branch
- Doe een checkout van de main-/master-branch
- Synchroniseer je lokale repository met het *git pull* commando
- Controleer of de wijzigingen van deel3 zichtbaar zijn in de main-branch
- Maak een nieuwe branch aan in je repository: *memyselfandi/new/deel4*
- Doe een checkout van deze nieuwe branch

## Inhoud (html)
In het index.html bestand, onder de sectie met de product cards, voorzie je de volgende structuur:

Een footer element met de klasse ‘footer’. Voorzie hierin:
- Een div element met de klasse ‘footer-header’.
  - Maak binnen deze div eerst een anchor element aan dat linkt naar de huidige pagina en de klasse ‘logo’ heeft.
    - Binnen het anchor element maak je een icon element aan die je de klasse ‘fas fa-shoe-prints’ geeft.
  - Maak vervolgens binnen deze footer-header nog een div element aan met volgende elementen:
    - Een heading van niveau 1 aan met de klasse ‘main-name’ en de tekst ‘Snaky Sneakers’.
    - Een paragraaf met de klasse ‘sub-name’ en de tekst ‘Sneaker reseller’.
        
    (Dit zijn dezelfde elementen die voorzien werden in de header).

- Een div element met de klasse ‘footer-social-media’ met hierbinnen volgend element:
  - Een ongeordende lijst met klasse ‘social-media’. Voorzie binnen deze lijst vier lijstitems met de klasse ‘social-media-item’, die de volgende structuur hebben:
    - Een anchor element dat linkt naar de huidige pagina en de klasse ‘social-media-link’ heeft.
    - Binnen dit element voorzie je een icon element. Dit element heeft binnen elke item een andere klasse: ‘fab fa-facebook-square’, ‘fab fa-instagram’, ‘fab fa-youtube’ of ‘fab fa-snapchat’.
- Een div element met de klasse ‘footer-copyright’. Voorzie hierbinnen een paragraaf met de klasse ‘footer-copyright-paragraph’ en de tekst “&copy; Copyright. Snaky Sneakers. All Rights Reserved.”

**Bekijk het resultaat in de browser**

## Opmaak
### Algemeen
#### _layout.scss
Selecteer het footer element op basis van haar klasse. Geef dit element als volgt vorm:
-	Een bovenste en onderste padding van 70px en een rechter en linker padding van 0.
-	Laad de mixin flexLayout in.
-	Zorg dat de elementen onder elkaar worden weergegeven.

### header
#### _layout.scss
Gebruik nesting om het element met klasse ‘footer-header’ te selecteren en geef het element als flex weer. 
Zorg er ook voor dat de items verticaal gecentreerd worden en geef het element een onderste margin van 70px.

### social-media
#### _layout.scss
Gebruik nesting om de ongeordende lijst te selecteren op basis van haar klasse. We gaan de lijst items nu horizontaal in een rij weergeven. Hiervoor passen we het volgende toe:
-	Flex weergave
-	Breedte van 300px
-	Zorg dat de ruimte tussen de elementen evenredig verdeeld wordt (‘space-between’).
-	Een onderste margin van 70px

Selecteer nu de lijstitems op basis van hun klasse en maak hierbij gebruik van nesting.
Zorg ervoor dat er geen bullet-points worden weergegeven.

Selecteer vervolgens de anchor elementen op basis van de klasse en maak ook hier gebruik van nesting. Zorg ervoor dat je de standaard stijl weghaalt en geef de elementen volgende eigenschappen:
-	Lettergrootte: 50px
-	Tekstkleur: ‘color-secondary’
-	Zorg voor een hover effect waarbij de tekstkleur wijzigt naar ‘color-primary’.
-	Gebruik een transitie op de tekstkleur van 0,7s.

### copyright
#### _layout.scss
Gebruik nesting om het element met klasse ‘footer-copyright-paragraph’ te selecteren en geef dit element volgende eigenschappen:
- Lettertype: font-josefinSans
- Lettergrootte: 18px
- Tekstkleur: color-secondary
- Laad de mixin textStyles in en geef het argument mee om telkens de eerste letter als een hoofdletter weer te geven.

## Resultaat
**Bekijk het resultaat in de browser!**

## Git branch
Wanneer je 100% tevreden bent over het resultaat doe je een commit en push van je branch *memyselfandi/new/deel4*. Gebruik als commit-message: *deel4 - footer*

Ga vervolgens naar je repository op github.com om een merge te doen van deze branch met je main-/master-branch.
