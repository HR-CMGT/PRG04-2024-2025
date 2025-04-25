# Les 2

Werken met classes en instances. Zie ook de presentatie.

- Oefenen met classes
- Expert opdracht: Whack a mole
- Links


<br><br><Br>

## Oefenen met classes

Je kan beginnen met de code uit het startproject:

```js
import {Engine,Actor,Vector} from "excalibur";
import {Resources,ResourceLoader} from "./resources.js";

export class Game extends Engine {

    constructor() {
        super({ width: 800, height: 600 })
        this.start(ResourceLoader).then(() => this.startGame())
    }

    startGame() {
        const fish = new Actor()
        this.add(fish)
        fish.graphics.use(Resources.Fish.toSprite())
        fish.pos = new Vector(20,20)
        fish.vel = new Vector(10,5)
    }
}
```

<br>

### Een Fish class aanmaken

- Maak een `Fish` class waarin de eigenschappen van de fish geplaatst worden.
- Let op dat de code voor de afbeelding, positie en snelheid van de fish nu niet meer in Game staan.
- Maak de snelheid en positie van de Fish random met `Math.random()`

```js
import {Actor,Vector} from "excalibur";
import {Resources} from "./resources.js";
export class Fish extends Actor {
    constructor(){
        console.log("I am a fish")
    }
    onInitialize(engine){
        // verplaats de fish eigenschappen van Game.js naar Fish.js
        // afbeelding, positie, snelheid
        // let op het gebruik van "this"
    }
}
```

<br>

### De fish toevoegen aan je game

- Voeg een instance van de fish class toe aan Game
- Gebruik een `for` loop om 10 vissen toe te voegen aan Game.

```js
import { Fish } from "fish.js"

class Game extends Engine {
    startGame() {
        const fish = new Fish()
        this.add(fish)
    }
}
```

<br>

### Een Shark class toevoegen

- Maak een Shark class
- De shark zwemt van links naar rechts
- Voeg de shark ook toe aan je game

<br>

### Bubbles toevoegen

- Maak een Bubble class
- De bubble beweegt van onder naar boven, vanaf een random x positie
- Voeg 10 bubbles toe aan de Game

<br><br><br>

## Expert opdracht: whack a mole

- [Maak het spelletje "whack a mole"](./les2-mole.md)

<br><br><br>

## Voorbeeldcode

- [Excalibur](https://excaliburjs.com)
- [CodePen Voorbeeld](https://codepen.io/eerk/pen/pvoWeqM?editors=0010)
- [Codesandbox Voorbeeld](https://codesandbox.io/s/excalibur-vite-testproject-olk4bu)

<br><br><br>

## Links

- [Excalibur](https://excaliburjs.com)
- [Documentatie](https://excaliburjs.com/docs/text/)
- [Git troubleshooting](../snippets/git.md)
