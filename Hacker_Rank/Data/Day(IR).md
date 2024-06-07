# Day 1: Interquartile Range

## Task

The interquartile range of an array is the difference between its first (**_Q1_**) and third (**_Q3_**)
quartiles (i.e., **_Q3_** - **_Q1_**).
Given an array, **_values_**, of **_n_** integers and an array, **_freqs_**, representing the respective
frequencies of **_values'_**s elements, construct a data set, **_S_**, where each **_values[i]_**
occurs at frequency **_freqs[i]_**. Then calculate and print **_S'_**s interquartile range, rounded
to a scale of **1** decimal place (i.e., **12.3** format).

**Tip**: Be careful to not use integer division when averaging the middle two elements for
a data set with an even number of elements, and be sure to not include the median in
your upper and lower data sets.
**Example**

**_values = [1,2,3]_**
**_freqs = [3,2,1]_**
Apply the frequencies to the values to get the expanded array **_S = [1,1,1,2,2,3]_**.
Here **_left = [1,1,1]_**, **_right = [2,2,3]_**. The median of the left half, **_Q1 = 1.0_**, the
middle element. For the right half, **_Q3 = 2.0_**. Print the difference to one decimal place:
**_Q3 - Q1 = 2.0 - 1.0 = 1_**, so print **1.0**.

## Solution

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class Result
{
    public static void interQuartile(List<int> values, List<int> freqs)
    {
        List<int> expandedData = new List<int>();
        for (int i = 0; i < values.Count; i++)
        {
            for (int j = 0; j < freqs[i]; j++)
            {
                expandedData.Add(values[i]);
            }
        }
        expandedData.Sort();
        int n = expandedData.Count;
        double Q1 = FindMedian(expandedData, 0, n / 2 - 1);
        double Q2 = FindMedian(expandedData, 0, n - 1); 
        double Q3 = FindMedian(expandedData, (n + 1) / 2, n - 1);
        double IQR = Q3 - Q1;
        Console.WriteLine(IQR.ToString("0.0"));
    }

    private static double FindMedian(List<int> data, int start, int end)
    {
        int count = end - start + 1;
        int mid = start + count / 2;

        if (count % 2 == 0)
        {
            return (data[mid - 1] + data[mid]) / 2.0;
        }
        else
        {
            return data[mid];
        }
    }
}

class Solution
{
    public static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine().Trim());
        List<int> val = Console.ReadLine().TrimEnd().Split(' ').ToList().Select(valTemp => Convert.ToInt32(valTemp)).ToList();
        List<int> freq = Console.ReadLine().TrimEnd().Split(' ').ToList().Select(freqTemp => Convert.ToInt32(freqTemp)).ToList();
        Result.interQuartile(val, freq);
    }
}
```
