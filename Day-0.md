# Day 0: Hello, World

## Task

To complete this challenge, you must save a line of input from stdin to a variable, print Hello, World. on a single line, and finally print the value of your variable on a second line

## Solution

```csharp
class Solution {
    static void Main(String[] args) {
        // Declare a variable named 'inputString' to hold our input.
        String inputString;

        // Read a full line of input from stdin (cin) and save it to our variable, input_string.
        inputString = Console.ReadLine();

        // Print a string literal saying "Hello, World." to stdout using cout.
        Console.WriteLine("Hello, World.");
        Console.WriteLine(inputString);
    }
}
```
