# Day 0: Mean, Median, and Mode

## Task

Given an array,**_X_** , of **_N_** integers, calculate and print the respective mean, median, and mode on separate lines. If your array contains more than one modal value, choose the numerically smallest one.

Note: Other than the modal value (which will always be an integer), your answers should be in decimal form, rounded to a scale of **1** decimal place (i.e.,**12.3, 7.0** format).

Example
**_ N = 6 _**
**_X = [1, 2, 3, 4, 5, 5]_**

The mean is **\( \frac{20}{6} \) = 3.3**.
The median is **\( \frac{3+4}{2} \) = 3.5**.
The mode is **5** because **5** occurs most frequently.

## Solution

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;

class Solution {
    static void Main(string[] args) {
        int n = Convert.ToInt32(Console.ReadLine());
        int[] arr = Array.ConvertAll(Console.ReadLine().Split(' '), int.Parse);
        double mean = CalculateMean(arr);
        Console.WriteLine(mean.ToString("F1"));
        double median = CalculateMedian(arr);
        Console.WriteLine(median.ToString("F1"));
        int mode = CalculateMode(arr);
        Console.WriteLine(mode);
    }

    static double CalculateMean(int[] arr) {
        int sum = arr.Sum();
        return (double)sum / arr.Length;
    }

    static double CalculateMedian(int[] arr) {
        Array.Sort(arr);
        int mid = arr.Length / 2;
        if (arr.Length % 2 == 0) {
            return (arr[mid - 1] + arr[mid]) / 2.0;
        } else {
            return arr[mid];
        }
    }

    static int CalculateMode(int[] arr) {
        Dictionary<int, int> frequency = new Dictionary<int, int>();
        foreach (int num in arr) {
            if (frequency.ContainsKey(num)) {
                frequency[num]++;
            } else {
                frequency[num] = 1;
            }
        }

        int maxFrequency = frequency.Values.Max();
        int mode = frequency.Where(x => x.Value == maxFrequency).Select(x => x.Key).Min();

        return mode;
    }
}
```
