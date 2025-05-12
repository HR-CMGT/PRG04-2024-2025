# Les 4 

- Inheritance
- Composition

<Br><Br><Br>

## Inheritance

Dit betekent dat een class automatisch de eigenschappen en functions van een andere class kan overnemen. In dit codevoorbeeld zie je dat de class `Robot` de eigenschappen van een `Actor` krijgt. 

```js
import { Actor } from "excalibur"

class Robot extends Actor {

}
```
Omdat de `Robot` nu een Excalibur `Actor` is, kan je de `onInitialize` functie gebruiken. Ook is er nu een `pos` en `vel` beschikbaar:
```js
import { Actor } from "excalibur"

class Robot extends Actor {
    onInitialize(){
        console.log(this.pos)
        console.log(this.vel)
    }
}
```
### Constructor en super()

Als je in jouw class `extends` gebruikt dan moet je het `super()` keyword toevoegen aan je constructor. In Excalibur wordt `super()` gebruikt om de hitbox aan de actor class door te geven.
```js
import { Actor } from "excalibur"

class Robot extends Actor {
    constructor() {
        super({width:100, height:100})
        console.log("ik ben een robot")
    }
}
```


<Br><Br><Br>

## Composition 

Composition houdt in dat je nadenkt over hoe je game is opgebouwd. Zitten al je actors in de main game class, of is het handiger dat een actor zelf ook weer child actors heeft? 

### Code voorbeeld

In dit code voorbeeld plaatsen we een `Car` Actor op een `Road` Actor.

```js
class Road extends Actor {
    onInitialize(){
        let c = new Car()
        this.addChild(c)
    }
}
```
<br><br><br>

# Oefening

![result](../images/chicken-result.png)

In de oefening plaatsen we kippen op een boomstam om te oefenen met inheritance en composition. De relaties tussen de classes kan je als diagram tekenen:

- Kip en Boomstam zijn Actors ***(Inheritance)***
- Game is Engine ***(Inheritance)***
- Game heeft Boomstammen ***(Composition)***
- Boomstam heeft kippen ***(Composition)***

![composition](../images/les6b.png)

<br>

### 🐔 Chicken on a raft

- Download met [excalibur chicken on a raft](https://github.com/HR-CMGT/prg4-chicken-on-a-raft)
- Volg de opdracht in de readme file.
- [Speel de theme song](https://www.youtube.com/watch?v=yVihOxP2QeY)

<br>
