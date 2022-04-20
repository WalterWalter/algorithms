### Preorder, Inorder, and Postorder Iterative traversal
##### Preorder Traversal (LC144)
```java
public List<Integer> preorderTraversal(TreeNode root) {
	List<Integer> list = new LinkedList<>();
	Stack<TreeNode> stack = new Stack<>();
	TreeNode cur = root;
	while (!stack.isEmpty() || cur != null) {
		if(cur != null) {
			list.add(cur.val);
			stack.push(cur);
			cur = cur.left;
		} else {
			TreeNode node = stack.pop();
			cur = node.right;
		}
	}
	return list;
}
```

##### Inorder Traversal (LC94)
```java
public List<Integer> inorderTraversal(TreeNode root) {
	List<Integer> list = new LinkedList<>();
	Stack<TreeNode> stack = new Stack<>();
	TreeNode cur = root;
	while (!stack.isEmpty() || cur != null) {
		if (cur != null) {
			stack.push(cur);
			cur = cur.left;
		} else {
			TreeNode node = stack.pop();
			list.add(node.val);
			cur = node.right;
		}
	}
	return list;
}
```
##### Postorder Traversal (LC145)
```java
public List<Integer> postorderTraversal(TreeNode root) {
	LinkedList<Integer> list = new LinkedList<>();
	Stack<TreeNode> stack = new Stack<>();
	TreeNode cur = root;
	while (!stack.isEmpty() || cur != null) {
		if (cur != null) {
			list.addFirst(cur.val);
			stack.push(cur);
			cur = cur.right;
		} else {
			TreeNode node = stack.pop();
			cur = node.left;
		}
	}
	return list;
}
```
##### Binary Search Tree Iterator (LC173)
```java
class BSTIterator {
    TreeNode cur;
    Stack<TreeNode> stack;
    
    public BSTIterator(TreeNode root) {
        cur = root;
        stack = new Stack<>();
    }
    
    /** @return the next smallest number */
    public int next() {
        int res = 0;
        while (cur != null || !stack.isEmpty()) {
            if (cur != null) {
                stack.push(cur);
                cur = cur.left;
            } else {
                TreeNode node = stack.pop();
                cur = node.right;
                res = node.val;
                break;
            }
        }
        
        return res;
    }
    
    /** @return whether we have a next smallest number */
    public boolean hasNext() {
        return cur != null || !stack.isEmpty();
    }
}
```

##### Related Problems: LC98. Validate Binary Search Tree