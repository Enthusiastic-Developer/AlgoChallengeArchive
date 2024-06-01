# Day 26: Nested Logic

## Task

Your local library needs your help! Given the expected and actual return dates for a library book, create a program that calculates the fine (if any). The fee structure is as follows:

1. If the book is returned on or before the expected return date, no fine will be charged (i.e.:**_fine = 0_** ).
2. If the book is returned after the expected return day but still within the same calendar month and year as the expected return date, **_fine = 15 Hackos x (the number of days late)_**.
3. If the book is returned after the expected return month but still within the same calendar year as the expected return date, the **_fine = 500 Hackos x (the number of months late)_**.
4. If the book is returned after the calendar year in which it was expected, there is a fixed fine of **_10000 Hackos_**.

## Solution

```csharp
using System;

class Solution {
    static void Main(String[] args) {
        // Read actual return date
        string[] actualDateInput = Console.ReadLine().Split(' ');
        int actualDay = int.Parse(actualDateInput[0]);
        int actualMonth = int.Parse(actualDateInput[1]);
        int actualYear = int.Parse(actualDateInput[2]);
        
        // Read expected return date
        string[] expectedDateInput = Console.ReadLine().Split(' ');
        int expectedDay = int.Parse(expectedDateInput[0]);
        int expectedMonth = int.Parse(expectedDateInput[1]);
        int expectedYear = int.Parse(expectedDateInput[2]);
        
        // Calculate the fine
        int fine = 0;
        
        if (actualYear > expectedYear) {
            // Returned after the calendar year
            fine = 10000;
        } else if (actualYear == expectedYear) {
            if (actualMonth > expectedMonth) {
                // Returned after the expected month but within the same year
                fine = 500 * (actualMonth - expectedMonth);
            } else if (actualMonth == expectedMonth && actualDay > expectedDay) {
                // Returned after the expected day but within the same month and year
                fine = 15 * (actualDay - expectedDay);
            }
        }
        
        // Output the fine
        Console.WriteLine(fine);
    }
}
```
