﻿# Day 11: 2D Arrays

## Task

Calculate the hourglass sum for every hourglass in **_A_**, then print the maximum hourglass sum

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

        List<List<int>> arr = new List<List<int>>();

for (int i = 0; i < 6; i++)
{
    arr.Add(Console.ReadLine().TrimEnd().Split(' ').ToList().Select(arrTemp => Convert.ToInt32(arrTemp)).ToList());
}

int maxHourSum = int.MinValue;

for (int i = 0; i < 4; i++)
{
    for (int j = 0; j < 4; j++)
    {
        int hourSum = arr[i][j] + arr[i][j + 1] + arr[i][j + 2] + arr[i + 1][j + 1] +
                       arr[i + 2][j] + arr[i + 2][j + 1] + arr[i + 2][j + 2];
        if (hourSum > maxHourSum)
        {
            maxHourSum = hourSum;
        }
    }
}
Console.WriteLine(maxHourSum);
    }
}
```
