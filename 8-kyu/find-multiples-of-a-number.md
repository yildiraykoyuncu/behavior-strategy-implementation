# [Find Multiples of a Number](https://www.codewars.com/kata/58ca658cc0d6401f2700045f)

This function finds a numbers multiples up to a determined number.

## Syntax

> findMultiples(`number`, `number`) -> `number`

### Parameters

**integer**: `number`

- The number you want to return list of its multiples.

**limit**: `number`

- Multiples of an integer can go to the infinity you need a limit to stop it.

### Return Value: `array`

- This function returns an array which contains the multiples of the integer we pass as an argument less equal than the limit we passed as the second argument.

## Examples

Function behavior is pretty simple, it returns an array of the multiples of the number passed as the first argument less equal than the number passed as second argument. It may be understood more clearly trough the examples.

description:

```js
// use case

const multiples = mumtiples(5, 25);
console.log(multiples) //[5, 10, 15, 20, 25]
```

```js
// use case

const multiples = mumtiples(3, 13);
console.log(multiples) //[3, 6, 9, 12]
```


> analyze a user's solution to this challenge

## [coldman](https://www.codewars.com/users/coldman)

```js
function findMultiples(int,limit){
  let result = []
  
  for (let i = int; i<=limit ; i+=int)
    result.push(i)
    
  return result
}
```

### Strategy

Coldman's strategy is starting with integer itself and keep adding integer until it reaches the limit. So every time it adds the integer it returns the next multiple of the integer. 

### Implementation

Coldman used a for loop starts with i = int and increases i with int at every iteration and pushes i to the result array until i is less equal than the limit. 

**function declaration**: Coldman declared a function with ES5 syntax.
 **for loop**: Coldman used a for loop to generate multiples of integer.

### Possible Refactors

This strategy could also be implemented by these;

- An arrow function
- while loop
- do while loop

---

> analyze another user's solution to this challenge

## [jsck2ky](https://www.codewars.com/users/jack2ky)

```js
function findMultiples(int,limit){
  var arr = [];
  for(var i = 1  ; limit >= i * int; i++ ){
    arr.push(i * int)
  }
  return arr
}
```

### Strategy

jack2ky used a similar logic with Coldman but instead of adding integer to itself at every iteration jack2ky chose multiplying integer with other integers starting from 1 and increasing by 1 every iteration. 

### Implementation

jack2ky used a for loop starts with i = 1 and increases i by 1 at every iteration multiplying i with integer and pushing the result to the arr array until i * integer reaches the limit set by the second argument of the function. 

**function declaration**: jack2ky declared function starting a for loop to compute multiples of the integer and push them to arr.
**for loop** jack2ky used a for loop to increase the i at every iteration and find the next multiple in line and stop the loop when it reaches to the limit.

### Possible Refactors

This strategy could also be implemented by these:

- Arrow function
- While loop
- do while loop

---

## Notes

write any notes to help you review this exercise later, and to help others' study it. this might include

- new vocabulary you learned
- the most important thing(s) you learned
- something that you still don't understand but want to keep studying
- something that surprised you
- tricks you will want to remember and use later
