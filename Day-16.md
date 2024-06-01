# Day 16: Exceptions - String to Integer

## Task

Read a string, **_S_**, and print its integer value; if **_S_** cannot be converted to an integer, print Bad String.

Note: You must use the String-to-Integer and exception handling constructs built into your submission language. If you attempt to use loops/conditional statements, you will get a **0** score.

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
        string S = Console.ReadLine();
        try
        {
            // Try to convert the string to an integer
            int number = int.Parse(S);
            // If successful, print the integer value
            Console.WriteLine(number);
        }
        catch (FormatException)
        {
            // If the string cannot be converted to an integer, print "Bad String"
            Console.WriteLine("Bad String");
        }
    }
}
```
