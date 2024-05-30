# Day 10: Binary Numbers

## Task

Given a base-**10** integer, **_n_** , convert it to binary (base-**2**). Then find and print the base-**10** integer denoting the maximum number of consecutive **1**'s in **_n_**'s binary representation. When working with different bases, it is common to show the base as a subscript.

Example
**_n = 12_**
The binary representation of **125<sub>10**</sub> is **1111101<sub>2</sub>**. In base **10**, there are **5** and **1** consecutive ones in two groups. Print the maximum, **5**.

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

            string  binary = Convert.ToString(n, 2);

            int maxCOnce = 0;

            int currentOnce = 0;

            for(int i = 0; i < binary.Length; i++)
            {
                if (binary[i] == '1')
                {
                    currentOnce++;
                    if(currentOnce > maxCOnce)
                    {
                        maxCOnce = currentOnce;
                    }
                }
                else
                {
                    currentOnce = 0;
                }
            }
            Console.WriteLine(maxCOnce);
        }
}
```
