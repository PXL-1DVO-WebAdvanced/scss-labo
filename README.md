# Labo SCSS
## Intro
In dit labo ga je zelf aan de slag en werk je in verschillende delen naar een groter resultaat toe. 
Doorheen dit labo worden er kleuren, lettertypes, teksten en afbeeldingen gebruikt. 
Je mag de voorgeschreven waardes gebruiken, maar voel je vrij om er je eigen 'touch' aan te geven.
Het doel van deze labo's is dat je stapsgewijs tot een resultaat komt, probeer daarom regelmatig naar het resultaat in de browser te kijken, zodat je ziet wat de code doet.

## Setup
### Git
- Clone deze repository en open de folder met de gewenste editor.
- Maak in de root folder van je project een nieuw bestand *.gitignore* met de volgende inhoud:

        node_modules
        css/main.css
        css/main.css.map
        .idea/

### Folders & files
- Maak een subfolder ***css*** aan
- Maak een subfolder ***scss*** aan
- Voeg het bestand ***main.scss*** aan toe aan de ***scss***-folder

### Node

- Initialiseer een nieuwe Node.js project door in de terminal het volgende commando uit te voeren:

        npm init -y

### Sass
- Installeer het Sass-package via npm
- Voeg een *dev*-script toe aan het *package.json*-bestand waarmee het *main.scss*-bestand gerecompiled wordt na elke wijziging. (Het gecompileerde *main.css* bestand moet in de subfolder *css* komen)
- Run dit script: 

      npm run dev

### Commit & Push
- Gebruik het commando *git commit* of je code-editor om een eerste commit te maken met als *message*: "init setup"
- Voer het *push*-commando uit om je commit ook te synchroniseren met je remote repository! Controleer dit in github.com.

