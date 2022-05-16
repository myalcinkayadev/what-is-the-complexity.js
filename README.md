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

```javascript
/*
  Time complexity:  O(n^2)
  Space complexity: O(n)
*/
const unique = (array) => {
  const newArray = [];

  // Time: O(n)
  for (let i = 0; i < array.length; i++) {
    const ele = array[i];
    /*
      In general searching through an array would require a linear scan. 
      It would have to technically iterate through the array to check does it include the given element.
    */
    // Time: O(n)
    if (!newArray.includes(ele)) {
      newArray.push(ele);
    }
  }

  return newArray;
}

/*
  Time complexity:  O(n + n) -> simplest form: O(n)
  Space complexity: O(n)
*/
// Better solution
const unique = (array) => {
  const onlyUniques = new Set();
  
  // Time: O(n)
  for (let i = 0; i < array.length; i++) {
    const ele = array[i];
    /*
      Adding an element into a set because it's a hashed data structure is going to give you a constant time operation
      In short: Inserting into a set is constant time
    */
    onlyUniques.add(ele); 
  }
  
  // Converts the set into array: Time: O(n)
  return Array.from(onlyUniques);
}
```
