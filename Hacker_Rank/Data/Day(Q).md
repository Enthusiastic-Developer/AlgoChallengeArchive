# Day 1: Quartiles

## Task

Given an array, **_arr_**, of **_n_** integers, calculate the respective first quartile (**_Q1_**), second
quartile (**_Q2_**), and third quartile (**_Q3_**). It is guaranteed that **_Q1, Q2,_** and **_Q3_** are
integers.
**Example**
**_arr = [9,5,7,1,3]_**
The sorted array is **[1,3,5,7,9]** which has an odd number of elements. The lower half
consists of **[1,3]**, and its median is **1+3/2 = 2**. The middle element is **5** and represents
the second quartile. The upper half is **[7,9]** and its median is **7+9/2 = 8**. Return **[2,5,8]**.
**_arr = [1,3,5,7]_**
The array is already sorted. The lower half is **[1,3]** with a median = **1+3/2 = 2**. The
median of the entire array is **3+5/2 = 4**, and of the upper half is **5+7/2 = 6**. Return
**[2,4,6]**.

## Solution

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class Result
{
    public static List<int> quartiles(List<int> arr)
    {
        arr.Sort();
        int n = arr.Count;
        int mid = n / 2;
        int Q2 = FindMedian(arr, 0, n);
        List<int> lowerHalf = arr.GetRange(0, mid);
        List<int> upperHalf = arr.GetRange((n % 2 == 0) ? mid : mid + 1, mid);
        int Q1 = FindMedian(lowerHalf, 0, lowerHalf.Count);
        int Q3 = FindMedian(upperHalf, 0, upperHalf.Count);
        return new List<int> { Q1, Q2, Q3 };
    }

    private static int FindMedian(List<int> arr, int start, int end)
    {
        int len = end - start;
        int mid = len / 2;
        if (len % 2 == 0)
        {
            return (arr[start + mid - 1] + arr[start + mid]) / 2;
        }
        else
        {
            return arr[start + mid];
        }
    }
}

class Solution
{
    public static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine().Trim());
        List<int> data = Console.ReadLine().TrimEnd().Split(' ').ToList().Select(int.Parse).ToList();
        List<int> res = Result.quartiles(data);
        Console.WriteLine(string.Join("\n", res));
    }
}
```
