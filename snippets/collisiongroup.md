# Collision Group

Om te voorkomen dat een speler door zijn eigen kogels geraakt kan worden, of dat spelers elkaar kunnen raken in een multiplayer game, kan je collision groups aanmaken. Hierin geef je aan welke colliders met welke andere colliders mogen botsen.

*player.js*
```js
import { CollisionGroupManager, CollisionGroup } from "excalibur"

export const playerCollisionGroup = CollisionGroupManager.create('player')

export class Player extends Actor {
  constructor() {
    super({
      name: 'player',
      pos: vec(200, 200),
      collisionType: CollisionType.Active,
      collisionGroup: playerCollisionGroup,
    })
  }
}
```

Met de helper function `collidesWith` can je aangeven welke groups met elkaar kunnen colliden. Let op dat je platforms ook kunnen colliden.

```js
const playerGroup = CollisionGroupManager.create('player')
const npcGroup = CollisionGroupManager.create('npcGroup')
const floorGroup = CollisionGroupManager.create('floorGroup')
const enemyGroup = CollisionGroupManager.create('enemyGroup')

const playersCanCollideWith = CollisionGroup.collidesWith([
  playersGroup, // collide with other players
  floorGroup, // collide with the floor
  enemyGroup, // collide with enemies
])

const enemiesCanCollideWith = CollisionGroup.collidesWith([
  playerGroup, // collide with players
  floorGroup, // collide with the floor
])

const npcGroupCanCollideWith = CollisionGroup.collidesWith([
  floorGroup, // only collides with the floor
])
```

Hieronder een vereenvoudigd voorbeeld waar je kan zien in welke group elke actor zit:

```js
const player = new Actor({
  collisionGroup: playersCanCollideWith,
})

const npc = new Actor({
  collisionGroup: npcGroupCanCollideWith,
})

const enemy = new Actor({
  collisionGroup: enemiesCanCollideWith,
})

const floor = new Actor({
  collisionType: CollisionType.Fixed
  collisionGroup: floorGroup,
})
```

<Br>

### Default collisions

⚠️ Een actor zonder `collisionGroup` krijgt als default: `CollisionGroup.All` (bots met alles).