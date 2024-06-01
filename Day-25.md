# Day 25: Running Time and Complexity

## Task

A prime is a natural number greater than **1** that has no positive divisors other than **1** and itself. Given a number, , determine and print whether it is **_Prime_** or **_Not prime_**.

Note: If possible, try to come up with a O(&radic;n) primality algorithm, or see what sort of optimizations you come up with for an *O(n)* algorithm. Be sure to check out the Editorial after submitting your code.

## Solution

```csharp
using System;
using System.Collections.Generic;

class Solution {
    static void Main(String[] args) {
        int numberOfTestCases = int.Parse(Console.ReadLine().Trim());
        List<int> testCases = new List<int>();
        
        for (int i = 0; i < numberOfTestCases; i++) {
            int number = int.Parse(Console.ReadLine().Trim());
            testCases.Add(number);
        }
        
        foreach (int number in testCases) {
            if (IsPrime(number)) {
                Console.WriteLine("Prime");
            } else {
                Console.WriteLine("Not prime");
            }
        }
    }
    
    static bool IsPrime(int number) {
        if (number <= 1) return false;
        if (number == 2 || number == 3) return true;
        if (number % 2 == 0 || number % 3 == 0) return false;
        
        for (int i = 5; i * i <= number; i += 6) {
            if (number % i == 0 || number % (i + 2) == 0) return false;
        }
        
        return true;
    }
}
```
