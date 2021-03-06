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


## Recursion
LC95 Unique Binary Search Trees II\
LC124 Binary Tree Maximum Path Sum\
LC235 Lowest Common Ancestor of a Binary Search Tree\
LC236 Lowest Common Ancestor of a Binary Tree\
LC250 Count Univalue Subtrees\
LC333\
LC100\
LC104\
LC105\
LC106\
LC108\
LC109\
LC110\
LC111\
LC112\
LC113\
LC129\
LC222\
LC226\
LC298\
LC366\
LC101\

