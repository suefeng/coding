# ES6 Generators

- Break the typical "run to completion" model for functions
- Generators can *pause* and *resume*, with **yield** and **next()**.
- Construct controlled-flow functions and iterators.

``` javascript
function* letterMaker() {
  yield "a";
  yield "b";
  yield "c";
}

let letterGen = letterMaker();
console.log(letterGen.next().value);
console.log(letterGen.next().value);
console.log(letterGen.next().value);
console.log(letterGen.next().value);
```

The console logs this:

``` javascript
a
b
c
undefined
```

A more efficient way:

``` javascript
function countMaker() {
  let count = 0;
  while(count < 3) {
    yield count += 1;
  }
}

let countGen = countMaker();
console.log(countGen.next().value);
console.log(countGen.next().value);
console.log(countGen.next().value);
console.log(countGen.next().value);
```

The console logs this:

``` javascript
1
2
3
undefined
```

## Adding a reset capability

``` javascript
function* evens() {
  let count = 0;
  while(true) {
    count += 2;
    let reset = yield count;
    if(reset) {
      count = 0;
    }
  }
}

let sequence = evens();
console.log(sequence.next().value);
console.log(sequence.next().value);
console.log(sequence.next().value);
console.log(sequence.next(true).value);
console.log(sequence.next().value);
```

The console logs this:

``` javascript
2
4
6
2
4
```

Another example:

``` javascript
const arrayIterator = (array) => {
  let index = 0;
  
  return {
    next: () => {
      if(index < array.length) {
        let next = array[index];
        index += 1;
        return next;
      }
    }
  }
}

let it = arrayIterator([1, 2, 3]);
console.log(it.next());
console.log(it.next());
console.log(it.next());
console.log(it.next());
```

The console logs this:

``` javascript
1
2
3
undefined
```

ES6 Generator:

``` javascript
function* arrayIterator() {
  yield arguments;
}
var it = arrayIterator(1, 2, 3);
console.log(it.next().value);
```

The console logs this:

``` javascript
[1, 2, 3];
```

To get them one at a time:

``` javascript
function arrayIterator() {
  for(let arg of arguments) {
    yield arg;
  }
}

var it = arrayIterator(1, 2, 3);
console.log(it.next().value);
console.log(it.next().value);
console.log(it.next().value);
```

The console logs this:

``` javascript
1
2
3
```

This can be simplified to this:

``` javascript
function* arrayIterator() {
  yield* arguments;
}

var it = arrayIterator(1, 2, 3);
console.log(it.next().value);
console.log(it.next().value);
console.log(it.next().value);
```



