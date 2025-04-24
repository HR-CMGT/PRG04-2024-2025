# Particles

Het is overzichtelijk om alle settings voor een particle emitter in een eigen class te zetten:

```js
import { ParticleEmitter, Color, EmitterType, Vector } from "excalibur"

export class Enginesmoke extends ParticleEmitter {
    constructor() {
        super({
            radius: 10,
            emitterType: EmitterType.Circle, 
            emitRate: 100, 
            isEmitting: true, 
            particle: {
                life: 1000, 
                opacity: 0.3, 
                fade: true, 
                beginColor: Color.Black, 
                endColor: Color.Blue, 
                minSize: 20, 
                maxSize: 15, 
                minSpeed: 50, 
                maxSpeed: 150, 
                minAngle: 0, 
                maxAngle: Math.PI * 2, 
            }
        });
        this.pos = new Vector(10,10)
    }   
}
```
Je kan nu een `EngineSmoke` instance toevoegen aan een Car:

```js
import { Actor } from "excalibur"
import { Enginesmoke } from "./enginesmoke.js";

export class Car extends Actor {
    addSmoke() {
        this.engineSmoke = new Enginesmoke();
        this.engineSmoke.emitRate = 100;
        this.addChild(this.engineSmoke);
    }
}
```