# Day 20: Sorting

## Task

Given an array, **_a_**, of size **_n_** distinct elements, sort the array in ascending order using the Bubble Sort algorithm above. Once sorted, print the following **3** lines:

1. Array is sorted in numSwaps swaps.

where **_numSwaps_** is the number of swaps that took place.

1. First Element: firstElement

where **_firstElement_** is the first element in the sorted array.

1. Last Element: lastElement

where **_lastElement_** is the last element in the sorted array.

Hint: To complete this challenge, you will need to add a variable that keeps a running tally of all swaps that occur during execution.

## Solution

```csharp
using System.CodeDom.Compiler;
using System.Collections.Generic;
using System.Collections;
using System.ComponentModel;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.IO;
using System.Linq;
using System.Reflection;
using System.Runtime.Serialization;
using System.Text.RegularExpressions;
using System.Text;
using System;

class Solution
{
    public static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine().Trim());

        List<int> a = Console.ReadLine().TrimEnd().Split(' ').ToList().Select(aTemp => Convert.ToInt32(aTemp)).ToList();

        int totalSwaps = 0;

        for (int i = 0; i < n; i++)
        {
            int numberOfSwaps = 0;

            for (int j = 0; j < n - 1; j++)
            {
                if (a[j] > a[j + 1])
                {
                    int temp = a[j];
                    a[j] = a[j + 1];
                    a[j + 1] = temp;
                    numberOfSwaps++;
                }
            }

            totalSwaps += numberOfSwaps;

            if (numberOfSwaps == 0)
            {
                break;
            }
        }

        Console.WriteLine($"Array is sorted in {totalSwaps} swaps.");
        Console.WriteLine($"First Element: {a[0]}");
        Console.WriteLine($"Last Element: {a[a.Count - 1]}");
    }
}
```
