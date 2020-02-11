# Classes in JavaScript

- Relate to each other through **inheritance**.
- Defined with the **class** keyword and uses a **constructor**
- The **extends** keyword creates child classes.

## The Lion King

``` javascript
Class Animal {...};
this.name;
this.height;
this.hello { log("Hi! I'm {this.name} from the land!")}
```

``` javascript
Class Lion {...} extends Animal
this.name;
this.height;
this.hello {
  log("Hi! I'm {this.name} from Pride Rock!");
}
```

``` javascript
class Animal {
  constructor(name, height) {
    this.name = name;
    this.height = height;
  }
}
let king = new Animal("Mufasa", 4.5);
console.log(king);
```

The console will log this:

``` javascript
Animal {name: "Mufasa", height: 4.5}
```

``` javascript
class Animal {
  constructor(name, height) {
    this.name = name;
    this.height = height;
  }
  hello() {
    console.log(`Hi! I'm ${this.name} from the Animal kingdom!`);
  }
}
let king = new Animal("Mufasa", 4.5);
king.hello();
```

The console will log this:

``` text
Hi! I'm Mufasa from the Animal kingdom!
```

``` javascript
class Animal {
  constructor(name, height) {
    this.name = name;
    this.height = height;
  }
  hello() {
    console.log(`Hi! I'm ${this.name} from the Animal kingdom!`);
  }
}
class Lion extends Animal {
  constructor(name, height, color) {
    super(name, height);
    this.color = color;
  }
}
let son = new Lion("Simba", 2, "golden");
console.log(son);
```

The console will log this:

``` javascript
Lion {name: "Simba", height: 2, color: "golden"}
```

Animal.js

``` javascript
class Animal { 
  constructor(name, height) {
    this.name = name;
    this.height = height;
  }
  hello() {
    console.log(`Hi! I'm ${this.name} from the Animal kingdom!`);
  }
}
```

index.js

``` javascript
import Animal from "./Animal";

class Lion extends Animal {
  constructor(name, height, color) {
    super(name, height);
    this.color = color;
  }
  hello() {
    console.log(`Hi! I'm ${this.name} from Pride Rock!`);
  }
}
let son = new Lion("Simba", 2, "golden");
son.hello();
```

The console logs this:

``` text
Hi! I'm Simba from Pride Rock!
```
