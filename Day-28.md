# Day 28: RegEx, Patterns, and Intro to Databases

## Task

Consider a database table, Emails, which has the attributes First Name and Email ID. Given **_N_** rows of data simulating the Emails table, print an alphabetically-ordered list of people whose email address ends in **_@gmail.com_**.

## Solution

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class Solution
{
    public static void Main(string[] args)
    {
        int N = Convert.ToInt32(Console.ReadLine().Trim());
        List<string> gmailUsers = new List<string>();

        for (int NItr = 0; NItr < N; NItr++)
        {
            string[] firstMultipleInput = Console.ReadLine().TrimEnd().Split(' ');
            string firstName = firstMultipleInput[0];
            string emailID = firstMultipleInput[1];

            if (emailID.EndsWith("@gmail.com"))
            {
                gmailUsers.Add(firstName);
            }
        }

        gmailUsers.Sort();

        foreach (string user in gmailUsers)
        {
            Console.WriteLine(user);
        }
    }
}
```
