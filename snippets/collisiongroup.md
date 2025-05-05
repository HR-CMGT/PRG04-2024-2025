# Collision Group

Om te voorkomen dat een speler door zijn eigen kogels geraakt kan worden, of dat spelers elkaar kunnen raken in een multiplayer game, kan je collision groups aanmaken. 

> *Actors in dezelfde collision group botsen niet met elkaar.*

<Br><br><br>

### Spelers onderling

Player actors botsen nu niet meer met andere Player actors:

`collidergroups.js`
```js
import { CollisionGroupManager } from "excalibur"

export const playerGroup = CollisionGroupManager.create('player')
```

`player.js`

```js
import { playerGroup } from "./collidergroups.js"

export class Player extends Actor {
  constructor() {
    super({
      collisionType: CollisionType.Active,
      collisionGroup: playerGroup,
    })
  }
}
```

<Br><br><br>

### Spelers en eigen kogels

Met de helper function `collidesWith` kan je aangeven welke groups niet met elkaar botsen. 

`collidergroups.js`
```js
import { CollisionGroup, CollisionGroupManager } from 'excalibur';

export const playerGroup = CollisionGroupManager.create('player');
export const bulletGroup = CollisionGroupManager.create('bullet');

// elementen in dezelfde group botsen NIET met elkaar
export const customGroup = CollisionGroup.collidesWith([playerGroup, bulletGroup]);
```
`player.js` en `bullet.js`
```js
import { customGroup } from "./collidergroups.js"

export class Player extends Actor {
  constructor() {
    super({
      collisionType: CollisionType.Active,
      collisionGroup: customGroup,
    })
  }
}
```

<Br><Br><Br>

### Default collisions

- Een actor *met* collisiongroup botst automatisch *niet* met actors in diezelfde group.
- Een actor *zonder* collisionGroup botst met alles (`CollisionGroup.All`).