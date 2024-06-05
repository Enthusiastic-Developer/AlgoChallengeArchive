# Day 18: Queues and Stacks

## Task

A palindrome is a word, phrase, number, or other sequence of characters which reads the same backwards and forwards. Can you determine if a given string,**_s_**, is a palindrome?

To solve this challenge, we must first take each character in **_s_**, enqueue it in a queue, and also push that same character onto a stack. Once that's done, we must dequeue the first character from the queue and pop the top character off the stack, then compare the two characters to see if they are the same; as long as the characters match, we continue dequeueing, popping, and comparing each character until our containers are empty (a non-match means **_s_** isn't a palindrome).

Write the following declarations and implementations:

1. Two instance variables: one for your **_stack_**, and one for your **_queue_**.
2. A void pushCharacter(char ch) method that pushes a character onto a stack.
3. A void enqueueCharacter(char ch) method that enqueues a character in the **_queue_** instance variable.
4. A char popCharacter() method that pops and returns the character at the top of the **_stack_** instance variable.
5. A char dequeueCharacter() method that dequeues and returns the first character in the **_queue_** instance variable.

## Solution

```csharp
class Solution {
    //Write your code here
private Stack<char> stack = new Stack<char>();
    private Queue<char> queue = new Queue<char>();

    // Pushes a character onto a stack
    public void pushCharacter(char ch) {
        stack.Push(ch);
    }

    // Enqueues a character in the queue
    public void enqueueCharacter(char ch) {
        queue.Enqueue(ch);
    }

    // Pops and returns the character at the top of the stack
    public char popCharacter() {
        return stack.Pop();
    }

    // Dequeues and returns the first character in the queue
    public char dequeueCharacter() {
        return queue.Dequeue();
    }
}
```
