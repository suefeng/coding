# ES6 Buit-In Helper Methods

## String Manipulation and Number Checking

- `String.repeat()` returns a new string of concatenated copies.
- **Searching** with startsWith, endsWith, includes, and more...
- **Number checking** for type and safety

``` javascript
let b = "wooh" + " ".repeat(50) + "oo";
console.log(b);
```

This outputs
`wooh`
`oo`
to the console.

``` javascript
let b = `woo${"oo".repeat(50)}`;
console.log(b);
```

This logs

``` text
woooooooooooooooooooooooooooooooooooooooooooooooooo
```

to the console.

``` javascript
console.log("butterfly".startsWith("butter"));
```

This logs `true` to the console.

``` javascript
const addToCart = (item, number) => {
  return Number.isFinite(number);
}
console.log(addToCart('shirt', Math.pow(2, 54)));
```

This logs `true` to the console.
But JavaScript is only safe up to 2^53. So when you use the .isSafeInteger function on it, it will display as `false`.
