**二叉树的三种遍历形式（非递归方式）**
==
前序遍历
--
  	//Definition for a binary tree node.
      public class TreeNode {
	    	int val;
	      TreeNode left;
	      TreeNode right;
	      TreeNode(int x) { 
		      val = x; 
				}
	    }

	class Solution {
    		public List<Integer> preorderTraversal(TreeNode root) {
        		Stack<TreeNode> stack = new Stack<>();
        		List<Integer> list = new ArrayList<>();
        		while (root != null || !stack.isEmpty()) {
            		while (root != null) {
                		stack.push(root);
                		list.add(root.val);
                		root = root.left;
            		}
            		root = stack.pop().right;
        		}
        		return list;
    	}
	}	
中序遍历
--
	class Solution {
    	public List<Integer> inorderTraversal(TreeNode root) {
        	Stack<TreeNode> stack = new Stack<>();
        	List<Integer> list = new ArrayList<>();
        	while (root != null || !stack.isEmpty()) {
            	while (root != null) {
                	stack.push(root);
                	root = root.left;
            	}
            	TreeNode node = stack.pop();
            	list.add(node.val);
            	root = node.right;
        	}
        	return list;
    	}
	}

后序遍历
--
	class Solution {
    	public List<Integer> postorderTraversal(TreeNode root) {
        	Stack<TreeNode> stack = new Stack<>();
        	LinkedList<Integer> list = new LinkedList<>();
        	while (root != null || !stack.isEmpty()) {
            	while(root != null) {
                	stack.push(root);
                	list.addFirst(root.val);
                	root = root.right;
            	}
            	root = stack.pop().left; 
        	}
        	return list;
    	}
	}
