# Data Structures in ES6

## Data Structures and Algorithms

- Algorithms solve various problems in different **running times**.
- Algorithms differ in their efficiency with **resource usage**.

## The Set

The set stores *unique* values.
Sets prove advantagious in storing **no duplicates**.

add, delete, has methods

``` javascript
let a = new Set();
a.add(5);
a.add(43);
a.add("Woohoo");
a.add({x: 50, y: 200});
console.log(a);
```

The console logs this:

``` javascript
Set {5, 43, "Woohoo", Object{x: 50, y: 200}}
```

All sets have a size property to determine the size.

``` javascript
console.log(a.size);
```

The console logs this:

``` text
4
```

``` javascript
console.log(a.has(5));
console.log(a.has(7));
```

The console logs this:

``` javascript
true
false
```

``` javascript
let numbers = [5, 7, 8, 13, 17];
let numSet = new Set(numbers);
console.log(numSet);
```

The console logs this:

``` javascript
Set {5, 7, 8, 13, 17}
```

``` javascript
for(let element of numSet.values()) {
  console.log(element);
}
```

The console logs this:

``` text
5
7
8
13
17
```

``` javascript
let chars = "awaerdsasdtewasdfewasd";
let chars_arr = chars.split("");
let chars_set = new Set(chars_arr);
console.log(chars_set);
```

This returns all the unique letters in an array, with each letter in its own cell.

## Maps

- Maps have **keys and values**.
- Maps share much similarity to objects.
- But maps beat objects with superior keys, and the size property.

``` javascript
let a = new Map();
let key_1 = "string key";
let key_2 = { a: "key" };
let key_3 = function() {};
a.set(key_1, "return value for a string key");
a.set(key_2, "return value for an object key");
a.set(key_3, "return value for an function key");
console.log(a);
```

The console logs this:

``` javascript
Map {"string key" => "return value for a string key", Object {a: "key"} => "return value for an object key", function => "return value for an function key"}
```

``` javascript
let numArr = [[1, 'one'], [2, 'two'], [3, 'three']];
let varMap = new Map(numArr);

for(let [key, value] of valMap.entries()) {
  console.log(`${key} points to ${value}`);
}
```

The console logs this:

``` text
1 points to one
2 points to two
3 points to three
```

``` javascript
let string = 'asdoienwasdoibhewlakdohte';
let letters = new Map();
for(let i = 0; i < string.length; i++) {
  let letter = string[i];
  if(!letters.has(letter)) {
    letters.set(letter, 1);
  } else {
    letter.set(letter, letters.get(letter) +1);
  }
}
console.log(letters);
```

The console logs something like this:

``` javascript
Map {"a" => 3, "o" => 3, "w" => 2, "e" => 3, "i" => 2...}
```

Maps are helpful when you need key value pairs.
