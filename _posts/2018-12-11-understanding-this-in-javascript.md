---
layout: post
title:  "Understanding this in JavaScript"
date:  2018-12-11
permalink: /:title/
---

Here is a snippet and [link to my favorite example](https://github.com/seanhelvey/snippets/tree/master/this) that you can use to understand `this` in JavaScript. Make sure you have the console open and read the logs as you click on the buttons. The code is [here in GitHub](https://github.com/seanhelvey/snippets/tree/master/this) as well.

```
console.log("window", this)

class Person {
    constructor (name, age) {
        this.name = name;
        this.age = age;

        this.makeOlderES5 = function(event) {
            console.log("makeOlderES5")
            console.log("this", this)
            console.log("event.target", event.target)
            this.age++;
            console.log("this.age", this.age)
        }

        this.makeOlderES6 = (event) => {
            console.log("makeOlderES6")
            console.log("this", this)
            console.log("event.target", event.target)
            this.age++;
            console.log("this.age", this.age)
        }
        console.log("person", this)
    }
}

let person = new Person("Jake", 55)

let buttonES5 = document.querySelector(".ES5")
buttonES5.addEventListener("click", person.makeOlderES5);

let buttonES6 = document.querySelector(".ES6")
buttonES6.addEventListener("click", person.makeOlderES6);
```



