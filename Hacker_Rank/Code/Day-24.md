# Day 24: More Linked Lists

## Task

A Node class is provided for you in the editor. A Node object has an integer data field, **_data_**, and a Node instance pointer, **_next_**, pointing to another node (i.e.: the next node in a list).

A removeDuplicates function is declared in your editor, which takes a pointer to the **_head_** node of a linked list as a parameter. Complete removeDuplicates so that it deletes any duplicate nodes from the list and returns the head of the updated list.

Note: The **_head_** pointer may be null, indicating that the list is empty. Be sure to reset your **_next_** pointer when performing deletions to avoid breaking the list.

## Solution

```csharp
  public static Node removeDuplicates(Node head)
    {
        if (head == null)
            return null;

        Node current = head;
        while (current.next != null)
        {
            if (current.data == current.next.data)
            {
                current.next = current.next.next;
            }
            else
            {
                current = current.next;
            }
        }
        return head;
    }
```
