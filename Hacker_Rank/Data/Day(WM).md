# Day 0: Weighted Mean

## Task

Given an array, **_X_**, of **_N_** integers and an array, **_W_**. representing the respective weights
of **_X's_** elements, calculate and print the weighted mean of **_X's_** elements. Your answer
should be rounded to a scale of 1 decimal place (i.e., **12.3** format).
**Example**
**_X = [1,2,3]_**
**_W = [5, 6, 7]_**
The array of values **_X[i] * W[i] = [5, 12, 21]._** Their sum is **38**. The sum of **_W = 18._**
The weighted mean is **38/18 = 2.11111...** Print **2.1** and return.
**Function Description**
Complete the weightedMean function in the editor below.
weightedMean has the following parameters:

- int X[N]: an array of values
- int W[N]: an array of weights
**Prints**
- float: the weighted mean to one decimal place

## Solution

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class Result
{
    public static void weightedMean(List<int> X, List<int> W)
    {
        int numerator = 0;
        for (int i = 0; i < X.Count; i++)
        {
            numerator += X[i] * W[i];
        }
        int denominator = W.Sum();
        double weightedMean = (double)numerator / denominator;
        Console.WriteLine(weightedMean.ToString("F1"));
    }
}

class Solution
{
    public static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine().Trim());
        List<int> vals = Console.ReadLine().TrimEnd().Split(' ').Select(int.Parse).ToList();
        List<int> weights = Console.ReadLine().TrimEnd().Split(' ').Select(int.Parse).ToList();
        Result.weightedMean(vals, weights);
    }
}
```
