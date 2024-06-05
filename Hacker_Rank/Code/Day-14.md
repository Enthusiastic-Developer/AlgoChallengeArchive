# Day 14: Scope

## Task

Complete the Difference class by writing the following:

A class constructor that takes an array of integers as a parameter and saves it to the **_elements_** instance variable.

A computeDifference method that finds the maximum absolute difference between any **2** numbers in **_elements_** and stores it in the **_maximumDifference_** instance variable.

## Solution

```csharp
    // Add your code here
    public Difference(int[] elements)
    {
        this.elements = elements;
        this.maximumDifference = 0; // Initialize maximumDifference
    }
    
    public void computeDifference()
    {
        // Initialize minimum and maximum with the first element in the array
        int min = elements[0];
        int max = elements[0];

        // Find the minimum and maximum values in the array
        for (int i = 1; i < elements.Length; i++)
        {
            if (elements[i] < min)
            {
                min = elements[i];
            }
            if (elements[i] > max)
            {
                max = elements[i];
            }
        }

        // Compute the maximum absolute difference
        maximumDifference = max - min;
    }
```
