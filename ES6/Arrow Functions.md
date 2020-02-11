# Arrow functions

## Syntax

`() => { … }`

By default, arrow functions are anonymous.

```javascript
function cheer() {
  console.log("Woohoo!")
}
cheer()
```

This outputs `Woohoo` to the console. It’s not anonymous because it’s a function declaration.

```javascript
var cheer = function() {
  console.log("Woohoo!")
}
cheer()
```

This outputs `Woohoo` to the console as well. But it isn’t performing a function declaration like in the previous example.

This is anonymous:

```javascript
setTimeout(function() {
  console.log("Woohoo!")
}, 3000)
```

```javascript
setTimeout(() => {
  console.log("Woohoo!")
}, 3000)
```

Both versions will output `Woohoo!` to the console.

```javascript
let cheer = () => {
  console.log("Woohoo!")
}
cheer()
```

This is still anonymous.
