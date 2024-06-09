# Day 2: Loops

## Task

1. First, print each vowel in **_s_** on a new line. The English vowels are a, e, i, o, and u, and
each vowel must be printed in the same order as it appeared in **_s_**.
2. Second, print each consonant (i.e., non-vowel) in **_s_** on a new line in the same order as
it appeared in **_s_**.

**Function Description**
Complete the vowelsAndConsonants function in the editor below.
vowelsAndConsonants has the following parameters:
• string s: the string to process

**Prints**
• Print each vowel of **_s_** in order on a new line, then print each consonant in order on a
new line. Return nothing.

**Input Format**
There is one line of input with the string **_s_**.

**Output Format**
First, print each vowel in **_s_** on a new line (in the same order as they appeared in **_s_**).
Second, print each consonant (i.e., non-vowel) in **_s_** on a new line (in the same order as
they appeared in **_s_**).

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
function vowelsAndConsonants(s) {
    const vowels = 'aeiou';
    for (let i = 0; i < s.length; i++) {
        if (vowels.includes(s[i])) {
            console.log(s[i]);
        }
    }
    for (let i = 0; i < s.length; i++) {
        if (!vowels.includes(s[i])) {
            console.log(s[i]);
        }
    }
}
function main() {
    const s = readLine();
    
    vowelsAndConsonants(s);
}
```
