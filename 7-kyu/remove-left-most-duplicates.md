# [Remove-left-most-duplicates](https://www.codewars.com/kata/5ba38ba180824a86850000f7)

Function this function deletes the duplicates in an array of integers starting from the left and leaving just the one on the last index.

## Syntax

> functionName(`number[]`, `number[]`) -> `number[]`

### Parameters

**Array of integers**: `number[]`

- An array of integers which will be cleaned from duplicating elements.

### Return Value: `number[]`

- An array of integers cleaned of duplicates leaving only the ones on the last indexes of each duplicating element.

## Examples

description:

It's a simple function can be used for quite a wide range of purposes. 

```js
// use case

const arr = [3,4,4,3,6,3];
const cleanedArr =solve(arr);
console.log(cleanedArr); // [4, 6, 3]
```

```js
// use case

const arr = [1,2,1,2,1,1,3];
const cleanedArr =solve(arr);
console.log(cleanedArr); // [2,1,3]
```

> analyze a user's solution to this challenge

## [haythem ker](https://www.codewars.com/users/haythem%20ker)

```js
function solve(arr){
    return arr.filter((val,i) => arr.lastIndexOf(val) == i);
}
```

### Strategy

Haythem used a cleaver and simple strategy to solve this task. He iterated over the array and in each iteration checked if the index of the iterated element is equals to it's last index in the array. He filtered the element based on the return value of this condition. 

### Implementation

He used .filter method to iterate over the array and return the elements meeting condition defined in the callback function.

**Array.filter() method**: It is used to filter duplicating elements in the array.

### Possible Refactors

very well implemented.

---

> analyze another user's solution to this challenge

## [JohanWiltink](https://www.codewars.com/users/JohanWiltink)

```js
const solve = a => Array.from(new Set(a.reverse())).reverse();
```

### Strategy

Johan approached the task from a different perspective. He turned the array into a set to clean duplications using the set's built feature that it does not contain any duplicating elements. To be sure that return value contains the elements at the last index he reversed the array before turning into a set. Then he turned the set into an array again and reversed it to have the correct order of elements in the array.

### Implementation

User implemented his strategy using set constructor and array constructor and Array.reverse() method.

**Array.from()**: It is used to turn the set into an array.
**new Set()**: It is used to turn Array into a set.
**Array.reverse()**: It is used to reverse the order of elements in the Array.

### Possible Refactors

Well implemented

---

## Notes

write any notes to help you review this exercise later, and to help others' study it. this might include

- new vocabulary you learned
- the most important thing(s) you learned
- something that you still don't understand but want to keep studying
- something that surprised you
- tricks you will want to remember and use later
