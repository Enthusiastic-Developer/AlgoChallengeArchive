# Day 19: Interfaces

## Task

The AdvancedArithmetic interface and the method declaration for the abstract divisorSum(n) method are provided for you in the editor below.

Complete the implementation of Calculator class, which implements the AdvancedArithmetic interface. The implementation for the divisorSum(n) method must return the sum of all divisors of **_n_**.

## Solution

```csharp
public class Calculator : AdvancedArithmetic
{
    public int divisorSum(int n)
    {
       int sum = 0;

        // Iterate from 1 to n and check if each number is a divisor of n
        for (int i = 1; i <= n; i++)
        {
            // If i is a divisor of n, add it to the sum
            if (n % i == 0)
            {
                sum += i;
            }
        }

        // Return the sum of divisors
        return sum;
    }
}
```
