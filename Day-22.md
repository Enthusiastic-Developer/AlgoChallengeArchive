# Day 22: Binary Search Trees

## Task

The height of a binary search tree is the number of edges between the tree's root and its furthest leaf. You are given a pointer, **_root_**, pointing to the root of a binary search tree. Complete the getHeight function provided in your editor so that it returns the height of the binary search tree.

## Solution

```csharp
static int getHeight(Node root)
    {
        if (root == null)
        {
            return -1;  // If there are no nodes, the height is -1
        }
        
        // Recursively find the height of left and right subtrees
        int leftHeight = getHeight(root.left);
        int rightHeight = getHeight(root.right);
        
        // The height of the current node is the greater of the two subtree heights, plus one for the current node
        return Math.Max(leftHeight, rightHeight) + 1;
    }
```
