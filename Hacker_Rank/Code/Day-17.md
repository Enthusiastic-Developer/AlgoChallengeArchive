# Day 17: More Exceptions

## Task

Write a Calculator class with a single method: int power(int,int). The power method takes two integers,**_n_**  and **_p_**, as parameters and returns the integer result of **_n<sup>p</sup>_**. If either **_n_** or **_p_** is negative, then the method must throw an exception with the message: n and p should be non-negative.

Note: Do not use an access modifier (e.g.: public) in the declaration for your Calculator class.

## Solution

```csharp
//Write your code here
class Calculator
{
    // Method to calculate n raised to the power of p
    public int power(int n, int p)
    {
        // Check if either n or p is negative
        if (n < 0 || p < 0)
        {
            // If either is negative, throw an exception with the specified message
            throw new ArgumentException("n and p should be non-negative");
        }

        // Calculate n raised to the power of p
        double result = Math.Pow(n, p);
        
        // Return the result as an integer
        return (int)result;
    }
}
```
