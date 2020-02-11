# You Don’t Need Loops in JavaScript

## 1. To Loop Through All Elements and Get an new modified array

Using loop:

``` javascript
var names = ["Jack", "Jecci", "Ram", "Tom"];
var upperCaseNames = [];
for(let i=0, totalNames = names.length; i< totalNames ; i= i +1) {
    upperCaseNames[i] = names[i].toUpperCase();
}
```

Without loop:

``` javascript
var names = ["Jack", "Jecci", "Ram", "Tom"];
var upperCaseNames = names.map(name => name.toUpperCase());
```

Note: If you’re using `map`, you cannot `break` or `continue` or `return` while looping. For this case, you should use `every` or `some`. Read about every and some in [this article](https://mariusschulz.com/blog/the-some-and-every-array-methods-in-javascript).

------

## 2. Loop through all elements and perform an action

Using loops

``` javascript
function print(name) {
   console.log(name);
}
var names = ["Jack", "Jecci", "Ram", "Tom"];
for(let i=0, totalNames = names.length; i< totalNames ; i= i +1) {
    print(names[i])
}
```

without loop

``` javascript
var names = ["Jack", "Jecci", "Ram", "Tom"];names.forEach(name=> print(name));
```

------

## 3. Filtering Array

Using normal `for` loop:

``` javascript
function isOdd(n) {
   return n %2;
}
var numbers = [1,2,3,4,5];
var odd = [];
for(let i=0, total = numbers.length; i< total ; i= i +1) {
   let number = numbers[i];
   if( isOdd(number) ) {
      odd.push(number);
   }}
```

Using `filter`:

``` javascript
var numbers = [1,2,3,4,5, 6, 7]var odd = numbers.filter(n => n%2); // single line
```

------

## 4. Creating an Output With Array Elements

Sum of numbers:

``` javascript
var numbers = [1,2,3,4,5]
var result = 0;
for(let i=0, total = numbers.length; i< total ; i= i +1) {
    result = result + numbers[i];
}
```

Using `reduce`:

``` javascript
var numbers = [1,2,3,4,5,6,7];
function sum(accumulator, currentValue){
   return accumulator + currentValue;
}
var initialVal = 0;
var result = numbers.reduce(sum, initialVal);
```

The above code can be even more simplified:

``` javascript
var numbers = [1,2,3,4,5,6,7, 10];
var result = numbers.reduce((acc, val)=> acc+val, 0);
```

------

## 5. Checking if an Array Contains a Value

``` javascript
var names = ["ram", "raj", "rahul"];
for(let i=0, totalNames = names.length; i< totalNames ; i= i +1) {
   if(names[i] === "rahul") {
     console.log("%c found rahul", "color:red");
     return; 
   }
}
```

Using `some`:

``` javascript
var names = ["ram", "raj", "rahul"];
let isRahulPresent = names.some(name => name==="rahul");
if(isRahulPresent) {
  console.log("%c found rahul", "color:red"); 
}
```

`%c` in the console statement will apply style to the console text. You can learn more about that in [this article](https://levelup.gitconnected.com/add-styles-and-formatting-to-your-console-log-messages-in-javascript-5f14819b1c5d).

------

## 6. To Check Whether Every Element in an Array Meets a Condition

Using `for` loop:

``` javascript
var num = [1,2,3,4,5, 0];
for(let i=0, total = numbers.length; i< total ; i= i +1) {    
    if(num <= 0) {      
        console.log("0 present in array");    
    }
}
```

Using `every`:

``` javascript
var num = [1,2,3,4,5, 0];
var isZeroFree = num.every(e => e > 0);
if(!isZeroFree) {
    console.log("0 present in array");
}
```

Thanks for reading. I hope you like this.