# Day 8: Dictionaries and Maps

## Task

Given **_n_** names and phone numbers, assemble a phone book that maps friends' names to their respective phone numbers. You will then be given an unknown number of names to query your phone book for. For each **_name_** queried, print the associated entry from your phone book on a new line in the form `name=phoneNumber`; if an entry for **_name_** is not found, print `Not found` instead.

**Note:** Your phone book should be a Dictionary/Map/HashMap data structure.

## Solution

```csharp
using System;
using System.Collections.Generic;
using System.IO;
class Solution 
{
    static void Main(String[] args)
        {
            int i = int.Parse(Console.ReadLine());

            Dictionary<string, string> phoneBook = new Dictionary<string, string>();

            for(int j=0; j<i; j++)
            {
                string[] entry = Console.ReadLine().Split();
                string name = entry[0];
                string phone = entry[1];

                phoneBook[name] = phone;
            }
            string query;
            while((query = Console.ReadLine()) != null)
            {
                if(phoneBook.TryGetValue(query, out string phone))
                {
                    Console.WriteLine($"{query}={phone}");
                }
                else
                {
                    Console.WriteLine("Not found"); 
                }
            }
        }
}
```
