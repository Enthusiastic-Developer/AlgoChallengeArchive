# Day 29: Bitwise AND

## Task

Given set **_S = {1,2,3,...,N}_**. Find two integers, **_A_** and **_B_** (where **_A<B_**), from set **_S_** such that the value of **_A&B_** is the maximum possible and also less than a given integer, **_K_**. In this case, **_&_** represents the bitwise AND operator.

## Solution

```csharp
using System;
using System.IO;

class Result
{
    /*
     * Complete the 'bitwiseAnd' function below.
     *
     * The function is expected to return an INTEGER.
     * The function accepts following parameters:
     *  1. INTEGER N
     *  2. INTEGER K
     */

    public static int bitwiseAnd(int N, int K)
    {
        int maxValue = 0;

        for (int A = 1; A <= N; A++)
        {
            for (int B = A + 1; B <= N; B++)
            {
                int andValue = A & B;
                if (andValue < K && andValue > maxValue)
                {
                    maxValue = andValue;
                }
            }
        }

        return maxValue;
    }
}

class Solution
{
    public static void Main(string[] args)
    {
        TextWriter textWriter = new StreamWriter(@System.Environment.GetEnvironmentVariable("OUTPUT_PATH"), true);

        int t = Convert.ToInt32(Console.ReadLine().Trim());

        for (int tItr = 0; tItr < t; tItr++)
        {
            string[] firstMultipleInput = Console.ReadLine().TrimEnd().Split(' ');

            int count = Convert.ToInt32(firstMultipleInput[0]);

            int lim = Convert.ToInt32(firstMultipleInput[1]);

            int res = Result.bitwiseAnd(count, lim);

            textWriter.WriteLine(res);
        }

        textWriter.Flush();
        textWriter.Close();
    }
}
```
