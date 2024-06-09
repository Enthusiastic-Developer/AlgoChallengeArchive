# Day 2: Conditional Statements: Switch

## Task

Complete the `getLetter(s)` function in the editor. It has one parameter: a string, **_s_**.
consisting of lowercase English alphabetic letters (i.e., `a` through `z`). It must return `A`, `B`, `C`,
or `D` depending on the following criteria:

1. If the first character in string **_s_** is in the set **_{a, e, i, o, u}_**, then return `A`.
2. If the first character in string **_s_** is in the set **_{b, c, d, f, g}_**, then return `B`.
3. If the first character in string **_s_** is in the set **_{h, j,k, l, m}_**, then return `C`.
4. If the first character in string **_s_** is in the set **_{n, p, g, r, s, t,v, w, x, y, z}_**, then return `D`.

**Hint:** You can get the letter at some index **_i_** in **_s_** using the syntax `s[i]` or `s.charAt(i)`.

**Function Description**
Complete the getLetter function in the editor below.
getLetter has the following parameters:
• string s: a string

**Returns**
• string: a single letter determined as described above

**Input Format**
Stub code in the editor reads a single string denoting s from stdin.

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

function getLetter(s) {
    let letter;
    const firstChar = s.charAt(0);
    switch (true) {
        case 'aeiou'.includes(firstChar):
            letter = 'A';
            break;
        case 'bcdfg'.includes(firstChar):
            letter = 'B';
            break;
        case 'hjklm'.includes(firstChar):
            letter = 'C';
            break;
        case 'npqrstvwxyz'.includes(firstChar):
            letter = 'D';
            break;
    }
    return letter;
}

function main() {
    const s = readLine();
    
    console.log(getLetter(s));
}
```
