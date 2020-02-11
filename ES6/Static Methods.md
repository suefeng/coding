# Static Methods

``` javascript
class Calculator {
  static multiply(a, b) {
    return a * b;
  }
}

let a = Calculator.multiply(5, 7);
console.log(a);
```

The console logs this:
`35`

``` javascript
class Calculator {
  static multiply(a, b) {
    return a * b;
  }
  static add(a, b) {
    return a + b;
  }
}

let a = Calculator.add(5, 7);
console.log(a);
```

The console logs this:
`12`
