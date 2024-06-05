# Day 2: Operators

## Task

Given the meal price (base cost of a meal), tip percent (the percentage of the meal price being added as tip), and tax percent (the percentage of the meal price being added as tax) for a meal, find and print the meal's total cost. Round the result to the nearest integer.

Example

- `mealcost` = 100
- `tippercent` = 15
- `taxpercent` = 8

A tip of 15% *100 = 15, and the taxes are 8%*100 = 8. Print the value `123` and return from the function.

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

class Result
{
    /*
     * Complete the 'solve' function below.
     *
     * The function accepts following parameters:
     *  1. DOUBLE meal_cost
     *  2. INTEGER tip_percent
     *  3. INTEGER tax_percent
     */
    public static void solve(double meal_cost, int tip_percent, int tax_percent)
    {
        double tipAmount = ((meal_cost / 100) * tip_percent);
        double taxAmount = ((tax_percent * meal_cost) / 100);
        double totalAmount = tipAmount + taxAmount + meal_cost;
        int roundOffAmount = (int)Math.Round(totalAmount);
        Console.WriteLine(roundOffAmount);
    }

}

class Solution
{
    public static void Main(string[] args)
    {
        double meal_cost = Convert.ToDouble(Console.ReadLine().Trim());
        int tip_percent = Convert.ToInt32(Console.ReadLine().Trim());
        int tax_percent = Convert.ToInt32(Console.ReadLine().Trim());
        Result.solve(meal_cost, tip_percent, tax_percent);
    }
}

```
