# Day 1: Let and Const

## Task

1. Declare a constant variable, **_PI**, and assign it the value Math.Pl. You will not pass this
challenge unless the variable is declared as a constant and named `PI` (uppercase).
2. Read a number, **_r_**, denoting the radius of a circle from stdin.
3. Use **_PI** and **_r_** to calculate the **_area_** and **_perimeter_** of a circle having radius r.
4. Print area as the first line of output and print **_perimeter_** as the second line of output.

**Input Format**
A single integer, **_r_**, denoting the radius of a circle.

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
    const PI = Math.PI;
    const radius = parseFloat(readLine());
    const area = PI * Math.pow(radius, 2);
    const perimeter = 2 * PI * radius;
    console.log(area);
    console.log(perimeter);
        try {    
            PI = 0;
            console.log(PI);
        } catch(error) {
            console.error("You correctly declared 'PI' as a constant.");
        }
    }
```
