# Day 13: Abstract Classes

## Task

Given a Book class and a Solution class, write a MyBook class that does the following:

Inherits from Book

Has a parameterized constructor taking these **3** parameters:

1. string **_title_**
2. string **_author_**
3. int **_price_**

Implements the Book class' abstract display() method so it prints these **3** lines:

1. **_Title:_**, a space, and then the current instance's **_title_**.
2. **_Author:_**, a space, and then the current instance's **_author_**.
3. **_Price:_**, a space, and then the current instance's **_price_**.

Note: Because these classes are being written in the same file, you must not use an access modifier (e.g.:**_public_** ) when declaring MyBook or your code will not execute.

## Solution

```csharp
//Write MyBook class
class MyBook : Book
{
    private int price; // Private field to store the price of the book

    // Constructor
    public MyBook(string title, string author, int price)
        : base(title, author) // Call the base class constructor
    {
        this.price = price; // Initialize the price
    }

    // Implementing the abstract display() method
    public override void display()
    {
        // Print the title, author, and price of the book in the required format
        Console.WriteLine("Title: " + title);
        Console.WriteLine("Author: " + author);
        Console.WriteLine("Price: " + price);
    }
}
```
