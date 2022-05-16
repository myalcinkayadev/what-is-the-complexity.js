# what-is-the-complexity.js

```javascript
/*
  Time complexity:  O(n)
  Space complexity: O(1) -> constant space
*/

const calculateAverage = (numbers) => {
  let sum = 0;

  for(let i = 0; i < numbers.length; i++) {
    let number = numbers[i];
    sum += number;
  }

  return sum / numbers.length;
}
```

```javascript
/*
  Time complexity:  O(n) 
  Space complexity: O(2n) -> simplest form: O(n)
*/

const double = (items) => {
  let newArray = [];

  for (let i = 0; i < items.length; i++) {
    newArray.push(items[i]);
    newArray.push(items[i]);
  }

  return newArray;
}
```

```javascript
/*
  Analyzing Recursive Code
  Our space complexity should consider the space taken by recursive calls on the call stack.
*/


/*
  Time complexity:  O(n)
  Space complexity: O(n)
*/
const zoom = (n) => {
  if (n === 0) {
    console.log('liftoff!');
    return;
  }

  console.log(n);
  zoom(n - 1);
}

zoom(10);
```

```javascript
/*
  Time complexity:  O(n - 2) -> simplest form: O(n)
  Space complexity: O(n)
*/
const zap = (n) => {
  if (n < 1) {
    console.log('blastoff!');
    return;
  }

  console.log(n);
  zap(n - 2);
}
```
