# [Find Multiples of a Number](https://www.codewars.com/kata/58ca658cc0d6401f2700045f)

This function simply compares correct answers with student answers and returns total score


## Syntax

> functionName(`array`, `array`) -> `number`

### Parameters

**array1**: `array`

- array1 contains the correct answers.

**array2**: `array`

- array2 contains the student answers.


### Return Value: `number`

Function returns total score of student.

## Examples

Function takes an array containing correct answers as the first argument and an array containing student's answers as the second argument. It compares arrays with each other and add 4 to final score for every correct answer and subtract 1 for every false answer then it returns final score at the end.

description:

```js
checkExam(["a", "a", "b", "b"], ["a", "c", "b", "d"]) // 6

```

```js
checkExam(["a", "a", "c", "b"], ["a", "a", "b",  ""]) // 7
```


---
---

> analyze a user's solution to this challenge

## [Fouad89](https://www.codewars.com/users/Fouad89)

```js
function checkExam(array1, array2) {
var score = 0;
  
  for (var i = 0; i < array1.length; i++){
  
    if (array1[i] == array2[i]) {
    score += 4;
    }else if (array2[i] === ""){
      score += 0
    }else {
    score -= 1
    }
 }
  
  if (score < 0) {score = 0}  
  return score
}
```

### Strategy

To pass that challenge Fouad89 uses reduce strategy. Basically it takes two arrays as argument and returns a score at the end. Fouad89 checked each element in correct answers array if it is equal to the corresponding element in the student answers array. For every match Fouad89 adds 4 points to the score otherwise subtracts 1 pont from it. It returns final score at the end.


### Implementation

Fouad89 used a for loop to loop trough both arrays and check if elements with same indexes are equal to each other. He also declared a score variable with an initial value of 0 to keep track of the final score. At each iteration if elements in both arrays are equal it adds 4 to score if they are not it subtracts 1 from it.



**function declaration**: A function with ES5 syntax
**for loop**: Loops trough both arrays and compare elements of it.

### Possible Refactors

- Arrow function
- Array.map method
- Array.reduce method

---



## [Kx7](https://www.codewars.com/users/Kx7)

```js
function checkExam(arr1, arr2) {
  let result = arr2.reduce((c, el, i) => el.length ? (el == arr1[i] ? c+4 : c-1) : c, 0);
  return result < 0 ? 0 : result;
}
```

### Strategy

Kx7 is using a similar strategy with Fouad89. Simply Kx7 operates on student answers array. He takes each answer and checks if it matches with correct answer and returns the total score at the end. He does not mutate result variable at each iteration.  

### Implementation

He used Array.reduce method instead of a loop. Basically function takes the student answers array (arr2) and reduces it to a final score. It keeps track of the score with accumulator in call-back function which is the first argument 'c'. Second argument in call-back function inside reduce method is 'el' which represents every element in the student answers array (arr2). And third argument in call-back function 'i' keeps track of the index of the elements in correct answers array (arr1) that will be matched with the 'el' of the student answers array.

Inside the call-back function Kx7 used ternary operator to set logical conditions. It first checks if el.length is 0 or not to see if student gave an answer to that question or he passed it. If 'el' is an empty string it returns 'c' accumulator without adding or subtracting any points which means 0 points for the questions not answered. If 'el' is not an empty string then it checks if it matches with the correct answer in arr1 which has the exact same index. If they match it returns c + 4, if they don't it returns c - 1. It repeats same process for all elements in arr2 then it returns the final version of the 'c'.

At the end function checks if the result is greater than 0 or not and returns 0 if its negative.

**function declaration**: He wrote function with function declaration syntax.
**Arrow functions**: He used arrow function syntax to write the call-back function in Array.reduce method
**Ternary operator**: He used ternary operator to set the logic that defines when give 4 points or 0 or -1.

### Possible Refactors

I can't think of any for now.
---

## Notes

- This is the first time I see current index argument in reduce methods call-back function is used. Its a good example to see how it can be useful if you are working on two arrays with reduce instead of using a for loop inside of it. 
