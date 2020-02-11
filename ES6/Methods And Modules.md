# Methods and Modules

## Helper Methods

- The map method creates new arrays by calling a function on individual elements in an original array.
- The filter method creates new arrays based on an original array and a certain test on each of its elements.

``` javascript
let values = [20, 30, 40]
let double = (n) => {
	return n*2
}

let doubled = values.map(double)
console.log(doubled)
```

This outputs `[40, 60, 80]` to the console.

### map helper method

``` javascript
let values = [20, 30, 40]
let doubled = values.map((n) => {
	return n*2
})
console.log(doubled)
```

This still outputs `[40, 60, 80]` to the console.

``` javascript
let values = [20, 30, 40]
let doubled = values.map((n) => return n*2)
console.log(doubled)
```

This still outputs `[40, 60, 80]` to the console.

``` javascript
let points = [7, 16, 21, 4, 3, 22, 5]
let highScores = points.filter((n) => {
	return n > 15
})
console.log(highScore)
```

This outputs `[16, 21, 22]` to the console.

``` javascript
let points = [7, 16, 21, 4, 3, 22, 5]
let highScores = points.filter((n) => n > 15)
console.log(highScore)
```

This outputs `[16, 21, 22]` to the console.

## Modules
Split code into unique files based on relevant data.
Handled in es6 via the export and import keywords.
