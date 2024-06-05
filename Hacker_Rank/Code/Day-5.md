# Day 5: Loops

## Task

Given an integer, **_n_** , print its first **10** multiples. Each multiple **_n x i_** (where **_1 <= i <= 10_** ) should be printed on a new line in the form: `n x i = result`.

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
        
        for(int i=1; i<=10; i++)
        {
            int result = n * i;
            Console.WriteLine($"{n} x {i} = {result}");
        }
    }
}
```
