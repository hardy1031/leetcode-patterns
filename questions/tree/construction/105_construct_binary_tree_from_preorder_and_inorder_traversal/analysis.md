# Analysis — 105. Construct Binary Tree from Preorder and Inorder Traversal

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/construction (divide and conquer)
Two traversals together uniquely determine a binary tree. preorder gives the root; inorder gives the left/right split.

## Layer 2 — Algorithms & Techniques
- Recursive divide and conquer: O(n²) naive, O(n) with hashmap
- **Insight:** `preorder[0]` is always the root. Find that value in `inorder` at index `mid` — everything left of `mid` is the left subtree, everything right is the right subtree. `mid` also tells you how many elements belong to the left subtree in `preorder`: `preorder[1:mid+1]` = left subtree preorder, `preorder[mid+1:]` = right subtree preorder.

## Layer 1 — Data Structures
- Implicit call stack (recursive)
- HashMap for O(1) inorder index lookup (optimization)

## Implementation

```python
def buildTree(self, preorder, inorder):
    if not preorder or not inorder:
        return None

    root = TreeNode(preorder[0])
    mid = inorder.index(preorder[0])

    root.left = self.buildTree(preorder[1:mid+1], inorder[:mid])
    root.right = self.buildTree(preorder[mid+1:], inorder[mid+1:])

    return root
```

## Complexity
- Time: O(n²) due to `inorder.index()` at each level; O(n) with a hashmap
- Space: O(n) for the recursion stack

## Key property to remember
- preorder: **root** → left → right (root is always first)
- inorder: left → **root** → right (root splits left/right)
- Together they uniquely reconstruct any binary tree with unique values.

## Related
- 106. Construct Binary Tree from Inorder and Postorder — same idea, postorder[-1] is the root
