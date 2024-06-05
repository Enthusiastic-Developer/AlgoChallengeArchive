# Day 12: Inheritance

## Task

You are given two classes, Person and Student, where Person is the base class and Student is the derived class. Completed code for Person and a declaration for Student are provided for you in the editor. Observe that Student inherits all the properties of Person.

Complete the Student class by writing the following:

A Student class constructor, which has  parameters:

1. A string,**_first name_** .
2. A string,**_last name_** .
3. An integer**_idNumber_**, .
4. An integer array (or vector) of test scores,**_scores_** .

A char calculate() method that calculates a Student object's average and returns the grade character representative of their calculated average:
Grading.png

## Solution

```csharp
class Student : Person{
    private int[] testScores;  
  
    /*	
    *   Class Constructor
    *   
    *   Parameters: 
    *   firstName - A string denoting the Person's first name.
    *   lastName - A string denoting the Person's last name.
    *   id - An integer denoting the Person's ID number.
    *   scores - An array of integers denoting the Person's test scores.
    */
    // Write your constructor here
    public Student(string firstName, string lastName, int id, int[] scores)
        : base(firstName, lastName, id)
    {
        testScores = scores;
    }
    /*	
    *   Method Name: Calculate
    *   Return: A character denoting the grade.
    */
    // Write your method here
    public char Calculate()
    {
        // Calculate the average score
        int sum = 0;
        int numScores = testScores.Length;

        for (int i = 0; i < numScores; i++)
        {
            sum += testScores[i];
        }

        // Calculate the average
        double average = (double)sum / numScores;

        // Determine the grade based on the average score
        if (average >= 90 && average <= 100)
        {
            return 'O';
        }
        else if (average >= 80)
        {
            return 'E';
        }
        else if (average >= 70)
        {
            return 'A';
        }
        else if (average >= 55)
        {
            return 'P';
        }
        else if (average >= 40)
        {
            return 'D';
        }
        else
        {
            return 'T';
        }
    }
}

```
