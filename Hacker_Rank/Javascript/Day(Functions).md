# Day 1: Functions

## Task

Implement a function named factorial that has one parameter: an integer, **_n_**. It must
return the value of **_n!_** (i.e., **_n_** factorial).

**Input Format**
Locked stub code in the editor reads a single integer, **_n_**, from stdin and passes it to a
function named factorial.

**Constraints**
• **1≤ n ≤ 10**

**Output Format**
The function must return the value of **_n!_**.

## Solution

```JavaScript
'use strict';

process.stdin.resume();
process.stdin.setEncoding('utf-8');
let inputString = '';
let currentLine = 0;
process.stdin.on('data', inputStdin => {
    inputString += inputStdin;
});
process.stdin.on('end', _ => {
    inputString = inputString.trim().split('\n').map(string => {
        return string.trim();
    });
    
    main();    
});
function readLine() {
    return inputString[currentLine++];
}
function main() {
    const n = +(readLine());
    
    console.log(factorial(n));
}
function factorial(n) {
    if (n === 0 || n === 1) {
        return 1;
    }
    return n * factorial(n - 1);
}
```
