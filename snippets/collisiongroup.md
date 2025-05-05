# Collision Group

Om te voorkomen dat een speler door zijn eigen kogels geraakt kan worden, of dat spelers elkaar kunnen raken in een multiplayer game, kan je collision groups aanmaken.

Hierin geef je aan welke colliders met welke andere colliders mogen botsen.

Maak een apart `collisiongroups.js` bestand aan in je project, hierin maak je de groups. Dit hoeft geen class te zijn omdat je alleen variabelen aanmaakt. 


*collisiongroups.js*
```js
import { CollisionGroupManager, CollisionGroup } from "excalibur"

const PlayerGroup = CollisionGroupManager.create('player')
const EnemyGroup = CollisionGroupManager.create('enemy')

export const PlayerCollisionGroup = CollisionGroup.collidesWith([
    EnemyGroup,
])

export const EnemyCollisionGroup = CollisionGroup.collidesWith([
    PlayerGroup,
    EnemyGroup,
])
```

Nu kan je in de actors van je game de group meegeven bij het aanmaken van de actor.

*enemy.js*
```js
import { EnemyCollisionGroup } from './collisiongroups.js'

export class Enemy extends Actor {
  constructor() {
    super({
      width: 32,
      height: 32,
      collisionType: ex.CollisionType.Active,
      collisionGroup: EnemyCollisionGroup,
    });
  }
}
```