# Day 6: Let's Review

## Task

Given a string, **_S_** , of length **_N_** that is indexed from **0** to **_N - 1_**, print its even-indexed and odd-indexed characters as **2** space-separated strings on a single line (see the Sample below for more detail).

**Note:** **0** is considered to be an even index.

## Solution

```csharp
using System;
using System.Collections.Generic;
using System.IO;
class Solution 
{
    static void Main(string[] args)
        {
            // Read the number of test cases
            int t = int.Parse(Console.ReadLine());

            // Iterate through each test case
            for (int testCase = 0; testCase < t; testCase++)
            {
                // Read the string for the current test case
                string inputString = Console.ReadLine();

                // Initialize strings for even-indexed and odd-indexed characters
                string evenIndexed = "";
                string oddIndexed = "";

                // Iterate through the string
                for (int i = 0; i < inputString.Length; i++)
                {
                    // If the index is even, append the character to evenIndexed
                    if (i % 2 == 0)
                    {
                        evenIndexed += inputString[i];
                    }
                    // If the index is odd, append the character to oddIndexed
                    else
                    {
                        oddIndexed += inputString[i];
                    }
                }

                // Print the even-indexed and odd-indexed characters as space-separated strings
                Console.WriteLine($"{evenIndexed} {oddIndexed}");
            }
        }
}
```
