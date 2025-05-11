# Type checking

Door type checking aan te zetten krijg je een meer stricte / strenge controle op je code. Je kan dan bijvoorbeeld geen functies aanroepen met de verkeerde waarden.

- Type checking in Javascript
- Type checking in Typescript

<br>
<br>
<br>

## Type checking in Javascript

### JSDoc comments

Je kan [JSDoc](https://jsdoc.app) type notatie gebruiken om types aan te duiden. Hieronder zie je voorbeelden voor classes en functies.

```javascript
import { Game } from "./game.js"
export class Bubble extends Actor {
    /**
     * @param {number} x
     * @param {number} y
     */
    constructor(x, y) {      // editor weet nu dat x,y numbers moeten zijn
        super({ x, y }) 
    }
    /**
     * @param { Game } engine
     */
    onInitialize(engine) {   // editor weet nu dat engine jouw Game is
    }
    
}
```
<br>
<br>
<br>

### CheckJS aanzetten

Door **checkJS** op `true` te zetten in krijg je advanced type checking. *In VS Code kan je in settings zoeken naar "checkJS"*. Als jouw editor dit niet heeft kan je het handmatig aanzetten in `jsconfig.json`.

JSCONFIG.JSON

```json
{
    "compilerOptions": {
        "checkJs": true,
    },
}
```

<br>
<br>
<br>

## Typescript

Typescript herkent automatisch types, dus je hoeft nu geen `@param` notatie meer te gebruiken. Excalibur is geschreven in Typescript dus dit werkt goed samen.

```bash
§ npm install typescript
```
Je bestanden geef je nu een `.ts` extensie en je gaat nu coderen in [typescript](https://www.typescriptlang.org). Door `npm run dev` of `npm run build` te doen, wordt dit automatisch omgezet naar javascript door `vite`. 

TSCONFIG.JSON
```json
{
  "compilerOptions": {
    "target": "ESNext",
    "useDefineForClassFields": true,
    "module": "ESNext",
    "lib": ["ESNext", "DOM"],
    "moduleResolution": "Node",
    "strict": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "esModuleInterop": true,
    "noEmit": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true,
    "skipLibCheck": true
  },
  "include": ["src"]
}
```

Je kan nu types rechtstreeks aanduiden in je functies. Hieronder zie je een voorbeeld van een game met typescript.

GAME.TS
```typescript
import { Actor, Engine, Loader } from "excalibur"
import { Resources } from "./resources"

export class Game extends Engine {

    showMessage(str : string) : void {
        console.log(`Hello ${str}`)
    }

    addNumbers(a : number, b : number) : number {
        return a + b
    }
}

export class Mario extends Actor {

    points:number

    onInitialize(engine : Game) : void {
        this.points = = 0
    }

    onPreUpdate(engine : Game) : void {
        
    }

    addPoints(points : number) : void {
        this.points++
    }
}

new Game()
```