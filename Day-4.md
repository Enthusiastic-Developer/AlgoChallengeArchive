# Day 4: Class vs. Instance

## Task

Write a Person class with an instance variable, **_age_**, and a constructor that takes an integer,**_initial Age_** , as a parameter. The constructor must assign **_initial Age_** to **_age_** after confirming the argument passed as **_initial Age_** is not negative; if a negative argument is passed as **_initial Age_**, the constructor should set **_age_** to **0** and print `Age is not valid, setting age to 0.`. In addition, you must write the following instance methods:

1. yearPasses() should increase the **_age_** instance variable by **1**.
2. amIOld() should perform the following conditional actions:
   - If **_age < 13_**, print `You are young.`.
   - If **_age >= 13_** and `age < 18`, print`You are a teenager.`.
   - Otherwise, print `You are old.`.
To help you learn by example and complete this challenge, much of the code is provided for you, but you'll be writing everything in the future. The code that creates each instance of your Person class is in the main method. Don't worry if you don't understand it all quite yet!

## Solution

```csharp
class Person {
    public int age;     
 public Person(int initialAge) {
        if(initialAge < 0)
        {
            Console.WriteLine("Age is not valid, setting age to 0.");
            age = 0;
        }
        else
        {
            age = initialAge;
        }
     }
     public void amIOld() {
        if(age < 13)
        {
            Console.WriteLine("You are young.");
        }
        else if(age >= 13 && age < 18)
        {
            Console.WriteLine("You are a teenager.");
        }
        else 
        {
            Console.WriteLine("You are old.");
        }
     }

     public void yearPasses() {
        age ++;
     }
```
