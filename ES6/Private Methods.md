# Private Methods

Example:

``` javascript
const budget = () => {
  let balance = 0;
  let changeBal = (val) => {
    return balance += val;
  }
  
  const deposit2 = () => changeBal(20);
  const withdraw20 = () => changeBal(-20);
  const check = () => balance;
  
  return {
    deposit20: deposit20,
    withdraw20: withdraw20,
    check: check
  }
}

let wallet = budget();
console.log(wallet);
wallet.deposit20();
console.log(wallet.check());
console.log(wallet.balance);
```

The console logs this:

``` javascript
Object {}
20
undefined
```

Furthur uses:

``` javascript
const budget = () => {
  let balance = 0;
  let changeBal = (val) => {
    return balance += val;
  }
  
  const deposit2 = () => changeBal(20);
  const withdraw20 = () => changeBal(-20);
  const check = () => balance;
  
  return { deposit20, withdraw20, check }
}

let wallet = budget();

wallet.deposit20();
wallet.withdraw20();
wallet.deposit20();
wallet.deposit20();
console.log(wallet.check());
```

The console logs this:

``` javascript
40
```

