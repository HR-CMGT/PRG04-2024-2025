# Collision Group

Actors in dezelfde collision group botsen niet met elkaar. Dit is handig voor players onderling of voor players en hun eigen bullets. Het werkt goed voor objecten waar heel veel van zijn, zoals coins.

`collisiongroups.js`
```js
import { CollisionGroupManager } from "excalibur"

export const friendsGroup = CollisionGroupManager.create('friends')
```

`player.js`

```js
import { friendsGroup } from "./collisiongroups.js"

export class Player extends Actor {
  constructor() {
    super({
      collisionType: CollisionType.Active,
      collisionGroup: friendsGroup,
    })
  }
}
```


<Br><Br><Br>

### Default collisions

- Een actor *met* collisiongroup botst automatisch *niet* met actors in diezelfde group.
- Een actor *zonder* collisionGroup botst met alles (`CollisionGroup.All`).
- Je kan per actor ook nog `CollisionType.Passive` of `CollisionType.PreventCollision` aanzetten.
