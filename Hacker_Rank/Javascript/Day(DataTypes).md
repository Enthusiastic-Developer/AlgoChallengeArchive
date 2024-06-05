# Day 0: Data Types

## Task

Variables named **_firstInteger, firstDecimal_**, and **_firstString-** are declared for you in the editor below. You must use the  operator to perform the following sequence of operations:

1. Convert **_secondInteger_** to an integer (Number type), then sum it with **_firstInteger_** and print the result on a new line using `console.log`.
2. Convert **_secondDecimal_** to a floating-point number (Number type), then sum it with **_firstDecimal_** and print the result on a new line using `console.log`.
3. Print the concatenation of **_firstString-** and **_secondString-** on a new line using `console.log`. Note that **_firstString-** must be printed first.

## Solution

```JavaScript
function performOperation(secondInteger, secondDecimal, secondString) {
    const firstInteger = 4;
    const firstDecimal = 4.0;
    const firstString = 'HackerRank ';
    console.log(firstInteger + Number(secondInteger));
    console.log(firstDecimal + Number(secondDecimal));
    console.log(firstString+secondString);
}
```
