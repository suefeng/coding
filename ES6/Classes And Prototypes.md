# Classes and Prototypes

## Object-Oriented Programming

- Objects or classes hold relevant data that interact with each other.
- Major languages like C, Java, and Ruby support OOP
- JavaScript supports a **prototypal inheritance model**.

## JavaScript Prototypes

- Classes are extractions on top of JavaScript prototypes.
- A **prototype** reveals an object's parent.
- All objects - Arrays, Dates, etc. - have a prototype.

``` javascript
function Wizard(name, house, pet) {
  this.name = name;
  this.house = house;
  this.pet = pet;
}
let harry = new Wizard("Harry Potter", "Gryffindor", "Owl");
console.log(harry);
```

The console logs this:

``` javascript
Wizard { name: "Harry Potter", house: "Gryffindor", pet: "Owl"}
```

``` javascript
function Wizard(name, house, pet) {
  this.name = name;
  this.house = house;
  this.pet = pet;
  this.greet = () => `I'm ${this.name} from ${this.house}`
}
let harry = new Wizard("Harry Potter", "Gryffindor", "Owl");
console.log(harry.greet);
```

The console logs this:

``` text
I'm Harry Potter from Gryffindor
```

``` javascript
function Wizard(name, house, pet) {
  this.name = name;
  this.house = house;
  this.pet = pet;
  this.greet = () => `I'm ${this.name} from ${this.house}`
}
Wizard.prototype.pet_name;
let harry = new Wizard("Harry Potter", "Gryffindor", "Owl");
harry.pet_name = "Hedwig";
console.log(harry);
```

The console logs this:

``` javascript
Wizard { house: "Gryffindor", name: "Harry Potter", pet: "Owl", greet:(), pet_name: "Hedwig" }
```

``` javascript
function Wizard(name, house, pet) {
  this.name = name;
  this.house = house;
  this.pet = pet;
  this.greet = () => `I'm ${this.name} from ${this.house}`
}
Wizard.prototype.pet_name;
Wizard.prototype.info = function() {
  return `I have a ${this.pet} named ${this.pet_name}`;
}
let harry = new Wizard("Harry Potter", "Gryffindor", "Owl");
harry.pet_name = "Hedwig";
console.log(harry.info());
```

The console logs this:

``` text
I have a Owl named Hedwig
```
