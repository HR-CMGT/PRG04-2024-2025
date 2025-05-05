# Collision Group

Om te voorkomen dat een speler door zijn eigen kogels geraakt kan worden, of dat spelers elkaar kunnen raken in een multiplayer game, kan je collision groups aanmaken.

Hierin geef je aan welke colliders met welke andere colliders mogen botsen.

Maak een apart `collisiongroups.js` bestand aan in je project, hierin maak je de groups. Volg daarin het volgende patroon. Hier zie je dat enemies met de floor kunnen colliden:


*collisiongroups.js*
```js
import { CollisionGroupManager, CollisionGroup } from "excalibur"

const enemyCategory = CollisionGroupManager.create('enemies');

export const enemyGroup = new CollisionGroup(
  enemyCategory.category,
  CollisionGroup.collidesWith([floorGroup])
);
```

Nu kan je in de actors van je game de group meegeven bij het aanmaken van de actor.

*enemy.js*
```js
import { enemyGroup } from './collisiongroups.js'

export class Enemy extends Actor {
  constructor() {
    super({
      width: 32,
      height: 32,
      collisionType: CollisionType.Active,
      collisionGroup: enemyGroup,
    });
  }
}
```

<Br>

### Default collisions

⚠️ Een actor zonder `collisionGroup` krijgt als default: `CollisionGroup.All` (bots met alles).

Zodra je een Actor wel een collisionGroup meegeeft moet je opletten dat alles waar je mee wil kunnen botsen in die group zit. Dus niet alleen vijanden maar ook alle platforms, hazards, etc. van je game.