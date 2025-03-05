# Scenes

## Wisselen tussen schermen

- In de `game` class kan je `scenes` toevoegen in plaats van `Actors`.
- Een `Scene` bevat `Actors` en je gameplay code.
- De game kan wisselen tussen scenes.
- Een Scene onthoudt de laatste state, dus als je heen en weer wisselt tussen twee scenes dan gaat de scene weer door op het vorige punt.

<br><br><br>

## Scenes

Als je een `Scene` aanmaakt dan voeg je de Actors op in de `onInitialize` functie. In de `onActivate` functie plaats je de code die uitgevoerd moet worden als er naar deze scene toe gesprongen wordt.

GAME.JS

```js
export class Game extends Engine {
    constructor(){
        super() 
        this.start(ResourceLoader).then(() => this.startGame())
    }
    startGame() {
        this.add('level', new Level())
        this.add('game-over', new GameOver())
        this.goToScene('level')
    }
}
```
LEVEL.JS

```js
export class Level extends Scene {
    onInitialize(engine) {
        this.add(new Enemy())
        this.add(new Ship())
    }
    onActivate(ctx) {
        console.log("reset het level")
    }
    gameOver(){
        this.engine.gotoScene('game-over')
    }
}
```

### Scene transitions

Je kan scenes laten outfaden / infaden:

```js
let transitions = {
    in: new FadeInOut({ duration: 400, direction: 'in', color: Color.Black }),
    out: new FadeInOut({ duration: 400, direction: 'out', color: Color.Black })
}
this.add('intro', { scene: new Intro(), transitions })
this.add('level', { scene: new Level(), transitions })
```

