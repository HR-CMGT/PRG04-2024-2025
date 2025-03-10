# Hulp vragen aan AI

- [Chat met de repository](#chat-met-de-repository)
- [CMGT chatbot](#cmgt-chatbot)
- [Prompting](#prompting)

<br><br><br>

## Chat met de repository

In [de github repository](https://github.com/HR-CMGT/PRG04-2024-2025/) kan je op het ***copilot*** icoontje klikken om een chatvenster te openen. Je kan dan specifieke vragen over de repository stellen. Zie dit screenshot voor een voorbeeld.

![copilot](../images/ai-github-assistent.png)

<br><br><br>

## CMGT Chatbot

Je kan aan de [CMGT chatbot](https://ai-assistent-mu.vercel.app) specifieke vragen stellen over ExcaliburJS. Zie dit screenshot voor een voorbeeld.

![vercel](../images/ai-vercel-assistent.png)

https://ai-assistent-mu.vercel.app

<br><br><br>

## Prompting

Je kan AI tools zoals ChatGPT een beter resultaat laten geven als je in de prompt de stijl van programmeren aangeeft:

```js
"Can you use this excaliburjs library to create a mario player class in OOP style in javascript? https://github.com/excaliburjs/Excalibur. You can use import { Actor } from "excalibur" to import the right classes from the library."
```

Je krijgt meestal niet meteen het gewenste resultaat. Bekijk het antwoord en vraag door om tot het juiste resultaat te komen dat voldoet aan de lesstof. Hieronder een voorbeeld:

> *Create a enemy class with a speed of 5*
```js
class Enemy {
    speed = 5
}
```
> *Thanks! That's cool but the enemy is not using excalibur, and it's not actually moving*

```js
class Enemy extends Actor {
    onInitialize(){
        this.vel = new Vector(5,0)
    }
}
```

<br><br><br>

## CMGPT Chatbot

Deze chatbot kent de lesstof en begrijpt dat je in OOP in Excalibur wil programmeren.

- [CMGT AI Chatbot](https://ai-assistent-mu.vercel.app)

<br><br><br>

## Links

- Blackbox.ai Javascript
- ChatGPT
- Codeium
- Copilot