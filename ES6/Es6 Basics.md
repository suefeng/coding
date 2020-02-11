# ES6 basics

## Variables

Using `let` instead of `var` lets you use scoping.
Example:

``` javascript
let limit = 100
{
	let limit = 10
  console.log('backstage limit', limit);
}
console.log('overall limit', limit);
```

This example will return the backstage limit as 10 (within the scope), while keeping the outer limit the same, 100.

If you use `var`, it will ignore the scope assignment as being only within the scope, and assign the value 10 to the outer limit as well.

`const` is used for constants that cannot be changed.

## Template literals

``` javascript
let a = 'good'
let greeting = `${a} morning`
console.log(greeting)
```

This should print “good morning” in the console.
