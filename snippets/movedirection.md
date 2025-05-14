# Traditionele beweging (Up, Down, Left Right)

Om een object in een bepaalde windrichting te laten bewegen kan je het object (tijdens elke update) een snelheid in een bepaalde richting geven.
Natuurlijk kan je achter `Keys` zelf aangeven met welke knoppen je het object wilt besturen (bijvoorbeeld: `W`, `A`, `S`, `D`)

```javascript
onPreUpdate(engine) {
  let xspeed = 0;
  let yspeed = 0;
  
  if (engine.input.keyboard.isHeld(Keys.Left)) {
      xspeed = -this.speed;
  }
  
  if (engine.input.keyboard.isHeld(Keys.Right)) {
      xspeed = this.speed;
  }
  
  if (engine.input.keyboard.isHeld(Keys.Up)) {
      yspeed = -this.speed;
  }
  
  if (engine.input.keyboard.isHeld(Keys.Down)) {
      yspeed = this.speed;
  }
  
  this.vel = new Vector(xspeed, yspeed);
}
```

## Beweging beperken

Als je wilt voorkomen dat het object het scherm uitgaat, kan je gebruik maken van de functie `clamp`. Deze zit in het Excalibur framework.

```javascript
this.pos.x = clamp(this.pos.x, this.width / 2, engine.drawWidth - this.width / 2);
this.pos.y = clamp(this.pos.y, this.width / 2, engine.drawHeight - this.height / 2);
```

# Een auto besturen

![draaien](../images/carangle.png)

Als je een auto bestuurt gebruik je `A`, `D` of ⬅️ ➡️ om de auto te draaien (`rotation`). Met de `W` of ⬆️ toets beweeg je in de richting waarin je gedraaid staat. Dit doe je door de `rotation` van de auto om te rekenen naar een `x,y` velocity.

![car](../images/car.png)


```javascript
import { Actor, Vector, Input } from "excalibur";
import { Resources } from "./resources.js";

export class Car extends Actor {
  onInitialize(engine) {
    this.graphics.use(Resources.Car.toSprite());
    this.pos = new Vector(400, 400);
  }

  onPreUpdate(engine) {
    let speed = 0;
    if (engine.input.keyboard.isHeld(Keys.Up)) {
        speed = 250;
    }
    if (engine.input.keyboard.isHeld(Keys.Right)) {
        this.rotation += 0.05;
    }
    if (engine.input.keyboard.isHeld(Keys.Left)) {
        this.rotation -= 0.05;
    }
    this.vel = Vector.fromAngle(this.rotation).scale(speed)
  }
}
```
<br>

- [Zie ook werken met Vectoren](./vector.md)
- [Compleet voorbeeld](./movedirection.md)
- [Codesandbox voorbeeld](https://codesandbox.io/p/sandbox/excalibur-move-direction-yr22q8)

