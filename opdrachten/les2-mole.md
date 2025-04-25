
## Expert opdracht: Whack a Mole

*Code uit één file omzetten naar Object Oriented Code*

Gebruik de volgende code: [Whack a Mole](https://github.com/HR-CMGT/PRG04-whack-a-mole). 
De code van dit spelletje staat allemaal in `src/game.js`. 
Wanneer je deze repository cloned of gebruik maakt van het [startproject](https://github.com/HR-CMGT/prg4-startproject-2024), voer dan nog het volgende uit in de terminal
```bash
npm install
npm run dev
```

Samen met een medestudent:
- bekijk je deze code en gaan jullie regel-voor-regel na wat de code doet.
- Bedenk welke class(es) je nodig hebt om de code op te delen in losse stukken.
- Bepaal wat de verantwoordelijkheid van deze class wordt.
- Schrijf hiervoor eerst de basis van de class

```javascript
import {Actor} from "excalibur";
import {Resources} from "./resources.js";

export class NameOfTheClass extends Actor {
    constructor() {
        super();
    }

    onInitialize(engine) {
        
    }
}
```

- Gebruik commentaar om aan te geven welk gedrag en welke eigenschappen de class moet gaan krijgen.

```javascript
import {Actor} from "excalibur";
import {Resources} from "./resources.js";

export class NameOfTheClass extends Actor {

    // the class needs speed
    constructor() {
        super();
    }

    onInitialize(engine) {
        // the car needs to use a sprite
    }

    // the class needs to move
}
```
- Werk nu samen de class uit en maak het spelletje werkend. 

<br><br><br>