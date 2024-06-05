# Day 23: BST Level-Order Traversal

## Task

A level-order traversal, also known as a breadth-first search, visits each level of a tree's nodes from left to right, top to bottom. You are given a pointer, **_root_**, pointing to the root of a binary search tree. Complete the levelOrder function provided in your editor so that it prints the level-order traversal of the binary search tree.

Hint: You'll find a queue helpful in completing this challenge.

## Solution

```csharp
static void levelOrder(Node root)
    {
        if (root == null)
        {
            return;
        }

        Queue<Node> queue = new Queue<Node>();
        queue.Enqueue(root);

        while (queue.Count > 0)
        {
            Node currentNode = queue.Dequeue();
            Console.Write(currentNode.data + " ");

            if (currentNode.left != null)
            {
                queue.Enqueue(currentNode.left);
            }

            if (currentNode.right != null)
            {
                queue.Enqueue(currentNode.right);
            }
        }
    }
```
