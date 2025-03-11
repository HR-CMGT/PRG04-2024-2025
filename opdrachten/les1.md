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

## Werken met import

In Vite projecten werk je met modules. Hierdoor kan je je javascript code opdelen in losse bestanden. Deze bestanden kan je met het `import` statement inladen in je project.

```js
import { Game } from "excalibur"

class Pong extends Game {
    // de Game code komt uit de excalibur library
}
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

[Kies een van de templates voor je eindproject](https://github.com/HR-CMGT/PRG04-2024-2025/blob/main/opdrachten/inleveropdracht.md)

<br>
<br>
<br>

## Voorbeeldcode

- [Excalibur](https://excaliburjs.com)
- [CodePen Voorbeeld](https://codepen.io/eerk/pen/pvoWeqM?editors=0010)
- [Codesandbox Voorbeeld](https://codesandbox.io/s/excalibur-vite-testproject-olk4bu)


<br>
<br>
<br>

## VS Code Tip

- Open "File > Preferences > Settings"
- Search "npm script"
- Toggle "Npm: Enable Script Explorer"
