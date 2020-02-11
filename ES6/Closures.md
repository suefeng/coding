# Closures

- Remember their creation environment and can reference independent variables within that environment.
- Enable **function factories**.
- Enable **private data**.

``` javascript
let call = () => {
  let secret = "ES6 rocks!";
}
console.log(secret);
```

This will return an error because it's not within the scope.

```javascript
let call = () => {
  let secret = "ES6 rocks!";
  let reveal = () => {
    console.log(secret);
  }
  return reveal;
}
let unveil = call();
unveil();
```

The console logs this:

```
ES6 rocks!
```

## Function Factory

``` javascript
const addSufix = (x) => {
  const concat = (y) => {
    return y + x;
  }
  return concat;
}

let add_ness = addSuffix("ness");
let h = add_ness("happi");
console.log(h);
```

The console logs this:

``` text
happiness
```

Can change the values to be this:

``` javascript
let add_ness = addSuffix("ful");
console.log(add_ness);
let f = add_ness("fruit");
console.log(f);
```

The console logs this:

``` text
fruitful
```

``` javascript
const product = x => y => y * x;
let mult5 = product(5);
console.log(mult5(3));
let double = product(2);
console.log(double(9));
```

The console logs this:

``` text
15
18
```

