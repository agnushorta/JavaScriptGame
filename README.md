
# [JavaScript Game Development Crash Course](https://www.youtube.com/watch?v=EvC3ge_puQk)

![tela](https://i.ibb.co/Ny7k5vq/Captura-de-tela-de-2022-07-15-22-46-19.png)


## Lesson I  - HTML & CSS setup

*index.html*

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Game</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <canvas id="canvas1"></canvas>

    <script src="script.js"></script>
</body>
</html>
```

*style.css*
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

#canvas1 {
    border: 5px solid black;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #4d79bc;
    max-width: 100%;
    max-height: 100%;
}
```

## Lesson II - Basic JavaScript Setup

*LOAD EVENT* fires whe the whole page has been loaded, including all dependent resources such as stylesheets and images.

*DRAWING CONTEXT* a built in object that contains all methods and properties that allow us to draw and animate colours, shapes and other graphics on HTML canvas.

*script.js*
```javascript
window.addEventListener('load', function(){
    // cavas setup
    const canvas = document.getElementById('canvas1');
    const ctx = canvas.getContext('2d');
    canvas.width = 500;
    canvas.height = 500;
});
```

## Lesson III - Object oriented programming with JavaScript

*OBJECT ORIENTED PROGRAMMING* which means we will wrap variables and functions in objects.

*JAVASCRIPT* is a prototype based object oriented language, which means it doesn't have classes, it has **prototypes**. We can use modern JavaScript syntax that introduced **classes** as so called **synthatical sugar** (simplified clean syntax that mimics classes from other progamming languages). Still under the hood it's just working with **prototype based inheritance**.

*ENCAPSULATION* is the bundling of data and the methods that act on that data in objects. Access to that data can be restricted from outside the bundle.

*script.js*
```javascript

    class InputHandler {

    }

    class Projectile {

    }

    class Particle {

    }

    class Player {
        constructor(game){
            this.game = game;
        }
    }

    class Enemy {

    }

    class Layer{

    }

    class Background{

    }

    class UI {

    }

    class Game {

    }
```

## Lesson IV - Creating player and game objects


*CONSTRUCTOR* is a epecial method on JavaScript class. When I call this JavaScript class later using **new** keyword, constructor will create one new blank JavaScript object and assign it properties and values based on the blue print inside.

*OBJECTS* in JavaScript are so called **reference data types**, which means that unlike primitive data types, they are dynamic in nature.

*CONSTRUCTOR* on JavaScript class is a special type of method, that will run once when we instanttiate the class using the new keyword. It will create one new blank object and it will give it values and properties as deined inside the blueprint here.

```javascript
 class Player {
        constructor(game){
            this.game = game;
            this.width = 120;
            this.height = 190;
            this.x = 20;
            this.y = 100;
            this.speedY = 0;
        }
        update(){
            this.y += this.speedY;
        }
        draw(context){
            context.fillRect(this.x, this.y, this. width, this.height);
        }
    }


    class Game {
        constructor(width, height){
            this.width = width;
            this.height = height;
            this.player = new Player(this);
        }
        update(){
            this.player.update();
        }
        draw(){
            this.player.draw(context);
        }
    }

    const game = new Game(canvas.width, canvas.height);
    ```

    ## Lesson V - Animation Loop (13:00)