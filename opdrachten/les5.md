# Les 5

## Communicatie tussen classes

  - Communicatie tussen game en actor
  - Waarden doorgeven
  - Communicatie tussen meerdere classes

<Br>
<Br>
<Br>


## Communicatie tussen game en actor

- Een `Actor` krijgt het `engine` argument in de `update` en `initialize` functies, dit verwijst naar jouw `game` class. 
- Je kan de game vanuit een actor ook altijd aanroepen via `this.scene.engine`.

```javascript
class Mario extends Actor {
    
    onInitialize(engine) {       
        engine.resetScore()
    }

    onPreUpdate(engine) {       
        if(this.pos.y > 1000) {
            engine.gameOver()
        }
    }

    hitCoin(){
        // in je eigen functies krijg je geen "engine", dus dan moet je "this.scene.engine" gebruiken.
        this.scene.engine.addPoint()
    }
}
```
GAME.JS

```javascript
class Game extends Engine {
    
    score = 0

    resetScore() {       
        this.score = 0
    }

    addPoint(){
        this.score++
    }

    gameOver(){
        console.log("game over!")
    }
}
```

<Br>
<Br>
<Br>


## Waarden doorgeven

Als je met `new` een instance aanmaakt dan kan je waarden doorgeven, die waarden komen binnen in de `constructor` van jouw class.

Positie meegeven aan BULLET.JS

```js
class Bullet extends Actor {
    constructor(x,y){
        super()
        this.pos = new Vector(x,y)
    }
}
```
alternatief
```js
class Bullet extends Actor {
    constructor(x,y){
        super({x, y})
    }
}
```
GAME.JS

```javascript
class Game extends Engine {
    
    startGame() {       
        let bullet = new Bullet(20,10)
        this.add(bullet)
    }
}
```


<Br>
<Br>
<Br>

## Communicatie tussen classes onderling

### Collision

Bij een collision krijg je een verwijzing naar de class waar je mee botst.

SHARK.JS
```js
export class Shark extends Actor {
    constructor(){
        super({ radius: 50 })
        this.on("collisionstart", (event) => this.onCollide(event))
    }

    onCollide(event) {
       if(event.other.owner instanceof Fish) {
           event.other.owner.hitByShark()
       }
    }
}
```
FISH.JS
```js
export class Fish extends Actor {
    hitByShark() {
       console.log("ARRGHH I was hit by a sharky boy 🦈")
    }
}
```

### Classes vinden via de Game

Je kan via `this.scene.engine` ook classes aanroepen die in de game beschikbaar zijn, zoals een `UI` class.

GAME.JS

```javascript
class Game extends Engine {
    
    ui   // ui moet een property zijn als je er van buitenaf bij wil kunnen
    
    startGame() {       
        this.ui = new UI()
        this.add(this.ui)

        let player = new Player()
        this.add(player)
    }
}
```
UI.JS
```javascript
class UI extends Actor {
    
    score = 0
    
    showScore(){
        console.log(this.score)
    }
}
```
PLAYER.JS
```javascript
class Player extends Actor {
    
    hitSomething(event){
        if(event.other.owner instanceof Coin) {
            this.scene.engine.ui.showScore()
        }
    }
}
```