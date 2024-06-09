# Day 2: Conditional Statements: If-Else

## Task

Complete the `getGrade (score)` function in the editor. It has one parameter: an
integer, **_score**, denoting the number of points Julia earned on an exam. It must return the
letter corresponding to her **_grade_** according to the following rules:

1. If **_25 < score ≤ 30_**, then **_grade = A_**.
2. If **_20 < score < 25_**, then **_grade = B_**.
3. If **_15 < score ≤ 20_**, then **_grade = C_**.
4. If **_10 < score < 15_**, then **_grade = D_**.
5. If **_5 < score < 10_**, then **_grade = E_**.
6. If **_0 < score < 5_**, then **_grade = F_**.

**Input Format**
Stub code in the editor reads a single integer denoting score from stdin and passes it to
the function.

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

function getGrade(score) {
    let grade;
    if (score > 25 && score <= 30) {
        grade = 'A';
    } else if (score > 20 && score <= 25) {
        grade = 'B';
    } else if (score > 15 && score <= 20) {
        grade = 'C';
    } else if (score > 10 && score <= 15) {
        grade = 'D';
    } else if (score > 5 && score <= 10) {
        grade = 'E';
    } else if (score >= 0 && score <= 5) {
        grade = 'F';
    }
    return grade;
}

function main() {
    const score = +(readLine());
    
    console.log(getGrade(score));
}
```
