# Operating and restructuring assignment

## spread operator: 

`{ … }`

``` javascript
let a = [20, 30, 40]
Let b = [10, …a, 50]
console.log(b)
```

It puts the array values of “a” inside “b”, and prints this to the console:
`[10, 20, 30, 40, 50]`

## Rest parameters

`function(…) { };`

``` javascript
function collect(...a) {
	console.log(a)
}
collect(1,2,3,4,5)
```

This converts those collection values into one array with those values:
`[1,2,3,4,5]`

## Destructuring Assignment

simplifies extracting data on arrays and objects into distinct variables

### Arrays

```javascript
let z = [4,5,6]
let [four, five] = z
console.log(four,five)
```

This outputs `4 5` to the console.

``` javascript
let animals = ["Simba", "Zazu", "Ed"]
let [lion, bird] = animals
console.log(lion, bird)
```

This outputs `Simba Zazu` to the console.

### Objects

``` javascript
let king = { name: "mufasa", kids: 1 }
let { name, kids } = king
console.log(name, kids)
```

This outputs `Mufasa 1` to the console.

``` javascript
let son = { name: "Simba, parents: 2 }
let name, parents
({ name, parents } = son)
console.log(name, parents)
```

This outputs `Simba 2` to the console.