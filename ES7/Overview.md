# Overviewing EcmaScript 2016

## ES7 New Features

- Exponent Operator

- More support for arrays

  

  ## Proposals for ES8

- More object manipulate with .values() and .entries().

- Async functions - better control flow beyond promises

``` shell
$ npm install babel-preset-es2016 --save-dev
```

``` javascript
let a = Math.pow(2, 5);
console.log(a);
```

The console logs this:

``` javascript
32
```

``` javascript
let b = "wonderful".includes("wonderful");
console.log(b);
```

The console logs this:

``` javascript
false
```

``` javascript
let b = [2, 3, 4, 5, 6].includes(4);
console.log(b);
```

The console logs this:

``` javascript
false
```

## ES8

``` shell
$ npm install babel-preset-es2017 --save-dev
```

``` javascript
let obj = { a: "one", b: "two", c: "three" };
let keys = Object.keys(obj);
console.log(keys);
```

The console logs this:

``` javascript
["a", "b", "c"]
```

``` javascript
let obj = { a: "one", b: "two", c: "three" };
let values = Object.values(obj);
console.log(values);
```

The console logs this:

``` javascript
["one", "two", "three"]
```

``` javascript
let obj = { a: "one", b: "two", c: "three" };
let entries = Object.entries(obj);
console.log(entries);
```

The console logs this:

``` javascript
[Array[2], Array[2], Array[2]]
```

Each one has a value and key inside.

``` javascript
let obj = { a: "one", b: "two", c: "three" };
let entries = Object.entries(obj);

for(let entry of entries) {
  console.log(`key: ${entry[0]}, value: ${entry[1]}`);
}
```

## Async

``` javascript
async function async_one() {
  return "one";
}
async_one().then(response => console.log(response));
```

The console logs this:

``` javascript
one
```



``` javascript
async function async_two() {
  throw new Error("Issue with async!");
}
async_two().catch(error => console.log(error));
```

The console logs this:

``` javascript
Error: Issue with async! at [insert stacktrace of the error location]
```

``` javascript
async function async_one() {
  return "one";
}
async_one().then(response => console.log(response));
```

## Await

``` javascript
async function async_three() {
  const one = await async_one();
  console.log(one);
  const two = await async_two();
  console.log(two);
}
async_three();
async function async_four() {
  const [res_one, res_two] = await Promise.all(
  	[async_one(), async_two()]
  )
  console.log(res_one, res_two);
}

async_four();
```

The console logs this:

``` javascript
one
two
one two
```

Await introduces asynchronous and sequential flow of logic, even if certain api calls take longer. Don't use it too much though, as it takes out the greatness of async in the first place, to put time taking code in the background.

