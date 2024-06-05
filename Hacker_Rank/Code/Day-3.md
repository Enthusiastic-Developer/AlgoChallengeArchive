# Day 3: Intro to Conditional Statements

## Task

Given an integer, `n`, perform the following conditional actions:

- If `n` is odd, print **Weird**
- If `n` is even and in the inclusive range of 2 to 5, print **Not Weird**
- If `n` is even and in the inclusive range of 6 to 20, print **Weird**
- If `n` is even and greater than 20, print **Not Weird**

Complete the stub code provided in your editor to print whether or not `n` is weird.

### Input Format

A single line containing a positive integer `n`.

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
        int N = Convert.ToInt32(Console.ReadLine().Trim());
        if(N % 2 == 1)
        {
            Console.WriteLine("Weird");
        }
        else if(N % 2 ==0 && N >= 2 && N <= 5)
        {
            Console.WriteLine("Not Weird");
        }
        else if(N % 2 ==0 && N >= 6 && N <= 20)
        {
            Console.WriteLine("Weird");
        }
        else if(N % 2 ==0 && N >= 20)
        {
            Console.WriteLine("Not Weird");
        }
    }
}

```
