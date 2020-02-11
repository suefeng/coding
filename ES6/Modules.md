# Modules

fellowship.js

``` javascript
const fellowship = ['Frodo', 'Samwise', 'Gandalf'];
const total = fellowship.length;
export { fellowship, total }
```

showfellowship.js

``` javascript
import { fellowship, total } from './fellowship';
console.log(fellowship, total);
```

This will log this to the console:

``` javascript
["Frodo", "Samwise", "Gandalf"]
3
```

math.js

``` javascript
const add = (a, b) => {
  return a + b;
}
const multiply = (a, b) => {
  return a * b;
}
export { add, multiply }
export default multiply;
```

index.js

``` javascript
import { add, multiply } from './math';
console.log(add(5,10));
console.log(multiply(5,10));
```

This will log this to the console:

``` text
15
50
```
