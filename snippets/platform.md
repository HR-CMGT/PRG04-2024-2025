## Van onderkant door platform springen. 

Als je op een platform wilt kunnen springen, kun je gebruik maken van de normale collision detection. Nadeel is alleen dat wanneer je vanaf de onderkant tegen een platform springt, 
je tegen de onderkant zal botsen. 

Om dit te voorkomen kan je de volgende code gebruiken:

```javascript
moveThrough(event) {
  const actor = event.other.owner;

  if(actor instanceof Player) {
    // velocity on y-axis is less then 0, so player is moving up
    if (actor.vel.y <= 0) {
      event.contact.cancel();
    }
  }
}
```
