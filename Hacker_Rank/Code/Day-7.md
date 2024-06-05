# Day 7: Arrays

## Task

Given an array,**_A_**, of **_N_** integers, print **_A_**'s elements in reverse order as a single line of space-separated numbers.

Example
**_A = [1,2,3,4]_**
Print `4 3 2 1`. Each integer is separated by one space.

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
        // Read the integer `n` from the input
            int n = Convert.ToInt32(Console.ReadLine().Trim());

            // Read the space-separated integers as a list
            List<int> arr = Console.ReadLine()
                                   .Trim()
                                   .Split(' ')
                                   .Select(int.Parse)
                                   .ToList();

            // Reverse the list
            arr.Reverse();

            // Join the reversed list into a single space-separated string
            string reversedString = string.Join(" ", arr);

            // Print the reversed string
            Console.WriteLine(reversedString);
    }
}
```
