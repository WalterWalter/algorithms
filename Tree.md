## Traversal
LC144 Bianry Tree Preorder Traversal (根左右)\
LC145 Binary Tree Postorder Traversal (左右根  = reverse（根右左）)\
LC94 Binary Tree Inorder Traversal\
LC173 Binary Search Tree Iterator\
LC102 Binary Tree Level Order Traversal (BFS, Queue)\
LC103 Binary Tree Zigzag Level Order Traversal (BFS, Double Stack)\
LC107 Binary Tree Level Order Traversal II (BFS, Queue, Insert to head)\

### Preorder, Inorder, and Postorder Iterative traversal
##### Preorder Traversal (LC144)
```java
public List<Integer> preorderTraversal(TreeNode root) {
    List<Integer> res = new ArrayList<>();
    Stack<TreeNode> stack = new Stack<>();
    while (root != null || !stack.isEmpty()) {
        while (root != null) {
            res.add(root.val);
            stack.push(root);
            root = root.left;
        }
        
        root = stack.pop();
        root = root.right;
    }
    
    return res;
}
```
##### Postorder Traversal (LC145)
```java
public List<Integer> postorderTraversal(TreeNode root) {
    List<Integer> res = new ArrayList<>();
    Stack<TreeNode> stack = new Stack<>();
    while (root != null || !stack.isEmpty()) {
        while (root != null) {
            res.add(root.val);
            stack.push(root);
            root = root.right;
        }
        
        root = stack.pop();
        root = root.left;
    }
    
    Collections.reverse(res);
    return res;
}
```
##### Inorder Traversal (LC94)
```java
public List<Integer> inorderTraversal(TreeNode root) {
    List<Integer> res = new ArrayList<>();
    Stack<TreeNode> stack = new Stack<>();
    while (root != null || !stack.isEmpty()) {
        while (root != null) {
            stack.push(root);
            root = root.left;
        }
        
        root = stack.pop();
        res.add(root.val);
        root = root.right;
    }
    
    return res;
}
```

## BST + 中序遍历
LC98 Validate Binary Search Tree\
LC99 Recover Binary Search Tree\
LC230 Kth Smallest Element in a BST\
LC285 Inorder Successor in BST\
LC272 Closest Binary Search Tree Value ||\
LC285&LC272有比遍历外更优的解法：https://leetcode.com/problems/closest-binary-search-tree-value-ii/discuss/70499/Java-5ms-iterative-following-hint-O(klogn)-time-and-space

## Mixed
LC257\
LC270\
LC199\
LC337\
LC255\
LC114\
LC156\
LC116\
LC117\
LC297\

## Recursion
LC95 Unique Binary Search Trees II\
LC124 Binary Tree Maximum Path Sum\
LC235 Lowest Common Ancestor of a Binary Search Tree\
LC236 Lowest Common Ancestor of a Binary Tree\
LC250 Count Univalue Subtrees\
LC333 Largest BST Subtree\
LC100 Same Tree\
LC104 Maximum Depth of Binary Tree\
LC105 Construct Binary Tree from Preorder and Inorder Traversal\
LC106 Construct Binary Tree from Inorder and Postorder Traversal\
LC108 Convert Sorted Array to Binary Search Tree\
LC109 Convert Sorted List to Binary Search Tree\
LC110 Balanced Binary Tree\
LC111 Minimum Depth of Binary Tree\
LC112 Path Sum\
LC113 Path Sum II\
LC129 Sum Root to Leaf Numbers\
LC222 Count Complete Tree Nodes\
LC226 Invert Binary Tree\
LC298 Binary Tree Longest Consecutive Sequence\
LC366 Find Leaves of Binary Tree\
LC101 Symmetric Tree\

