# Day 15: Linked List

## Task

Complete the insert function in your editor so that it creates a new Node (pass **_data_** as the Node constructor argument) and inserts it at the tail of the linked list referenced by the **_head_** parameter. Once the new node is added, return the reference to the **_head_** node.

Note: The **_head_** argument is null for an empty list.

## Solution

```csharp
public static Node insert(Node head, int data)
{
    // Create a new node with the given data
    Node newNode = new Node(data);

    // If the list is empty (head is null), return the new node as the head
    if (head == null)
    {
        return newNode;
    }

    // Otherwise, traverse the list to find the last node
    Node current = head;
    while (current.next != null)
    {
        current = current.next;
    }

    // Append the new node to the end of the list
    current.next = newNode;

    // Return the head of the list
    return head;
}
```
