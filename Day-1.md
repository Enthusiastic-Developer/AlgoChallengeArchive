# Day 1: Data Types

## Task

Complete the code in the editor below. The variables `i`, `d`, and `s` are already declared and initialized for you. You must:

1. Declare 3 variables: one of type int, one of type double, and one of type String.
2. Read 3 lines of input from stdin (according to the sequence given in the Input Format section below) and initialize your 3 variables.
3. Use the `+` operator to perform the following operations:
   - Print the sum of `i` plus your int variable on a new line.
   - Print the sum of `d` plus your double variable to a scale of one decimal place on a new line.
   - Concatenate `s` with the string you read as input and print the result on a new line.

## Solution

```csharp
// Declare second integer, double, and String variables.
        int intInput;
        double doubleInput;
        string stringInput;
        // Read and save an integer, double, and String to your variables.
        intInput = Convert.ToInt32(Console.ReadLine());
        doubleInput = Convert.ToDouble(Console.ReadLine());
        stringInput = Console.ReadLine();
        // Print the sum of both integer variables on a new line.
        Console.WriteLine(i + intInput);
        // Print the sum of the double variables on a new line.
        Console.WriteLine((d + doubleInput).ToString("0.0"));
        // Concatenate and print the String variables on a new line
        // The 's' variable above should be printed first.
        Console.WriteLine(s + stringInput);
```
