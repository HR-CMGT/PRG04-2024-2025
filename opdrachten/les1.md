# Les 1

- Introductie vak, cursushandleiding, toetsing
- Introductie modern web development. 
- Uitchecken van het Vite Excalibur template project in VS Code. 
- Werken met npm run dev
- Werken met modules en `import`, `export`.

<br>
<br>
<br>

## Voorbereiding

- Installeer [Node.js](https://nodejs.org/en/download/)
- Installeer [Visual Studio Code](https://code.visualstudio.com/download)
- Zorg dat je een github account hebt en dat je bent ingelogd.

<br>
<br>
<br>

## Modern Web Development

Introductie werken met [Vite](https://vite.dev) en modules.

<br>
<br>
<br>



## Excalibur project

- Ga naar het [excalibur startproject](https://github.com/HR-CMGT/prg4-startproject-2024)
- Klik op ***use this template > Create a new repository***
- Ga naar het project toe in je eigen github pagina.
- Klik op ***Code*** en kopieer de `.git` url.
- Open Visual Studio Code, klik op ***Files > Clone repository***
- Het project wordt nu gedownload naar je eigen projectmap.
- Open een terminal en typ `npm install`
- Start de dev server met `npm run dev`.
- Stop de dev server met `ctrl + c`

<br>
<br>
<br>

## Werken met import en export

In Vite projecten werk je met modules. Hierdoor kan je je javascript code opdelen in losse bestanden. Deze bestanden kan je met het `import` statement inladen in je project.

Dit geldt zowel voor het werken met libraries zoals Excalibur, maar ook voor je eigen code. Je kan alleen code importeren waar een `export` statement is gebruikt.

```js
import { Game } from "excalibur"

class Pong extends Game {
    // de Game code komt uit de excalibur library
}
```

Je kan ook code uit je eigen JS files importeren, dan moet je opletten dat je ook `export` gebruikt.

```js
export class Knakworst {
    constructor() {
        console.log("the worst case")
    }
}
```
```js
import { Knakworst } from "knakworst.js"

let k = new Kwakworst()
```


<br>
<br>
<br>

## Opdracht

- Voeg een aantal PNG's toe aan je project in de `public` folder. 
- Laad de afbeeldingen in `resources.js`
- Maak een Actor voor de achtergrondafbeelding
- Plaats Actors op de voorgrond met een position en een velocity
- Verwijder of verplaats de actors als er op geklikt wordt
- Maak een FOR loop om heel veel actors te plaatsen. Zorg dat ze allemaal ergens anders staan en anders bewegen.

<br>
<br>
<br>

## Voorbereiding inleveropdracht

[Kies een van de templates voor je eindproject](https://github.com/HR-CMGT/PRG04-2022-2023/blob/main/opdrachten/inleveropdracht.md)

<br>
<br>
<br>

## VS Code Tip

- Open "File > Preferences > Settings"
- Search "npm script"
- Toggle "Npm: Enable Script Explorer"


<br>
<br>
<br>

## Links

- [Game Art](https://opengameart.org) en [Kenney](https://www.kenney.nl/assets)
- [Excalibur](https://excaliburjs.com)
- [Codesandbox Excalibur playground](https://codesandbox.io/s/excalibur-vite-testproject-olk4bu)
- [Documentatie](https://excaliburjs.com/docs/text/).  
- [Git troubleshooting](../snippets/git.md)

