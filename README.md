二叉树的三种遍历形式（非递归方式）
======
前序遍历
----
\/**<br>
\* Definition for a binary tree node.<br>
\* public class TreeNode {<br>
\*     int val;<br>
\*     TreeNode left;<br>
\*     TreeNode right;<br>
\*     TreeNode(int x) { val = x; }<br>
\* }<br>
\*/<br>
class Solution {<br>
    public List<Integer> preorderTraversal(TreeNode root) {<br>
        Stack<TreeNode> stack = new Stack<>();<br>
        List<Integer> list = new ArrayList<>();<br>
        while (root != null || !stack.isEmpty()) {<br>
            while (root != null) {<br>
                stack.push(root);<br>
                list.add(root.val);<br>
                root = root.left;<br>
            }<br>
            root = stack.pop().right;<br>
        }<br>
        return list;<br>
    }<br>
}<br>

中序遍历
---
\/**<br>
\* Definition for a binary tree node.<br>
\* public class TreeNode {<br>
\*     int val;<br>
\*     TreeNode left;<br>
\*     TreeNode right;<br>
\*     TreeNode(int x) { val = x; }<br>
\* }<br>
\*/<br>
class Solution {<br>
    public List<Integer> inorderTraversal(TreeNode root) {<br>
        Stack<TreeNode> stack = new Stack<>();<br>
        List<Integer> list = new ArrayList<>();<br>
        while (root != null || !stack.isEmpty()) {<br>
            while (root != null) {<br>
                stack.push(root);<br>
                root = root.left;<br>
            }<br>
            TreeNode node = stack.pop();<br>
            list.add(node.val);<br>
            root = node.right;<br>
        }<br>
        return list;<br>
    }<br>
}<br>

后序遍历
---
\/**<br>
\* Definition for a binary tree node.<br>
\* public class TreeNode {<br>
\*     int val;<br>
\*     TreeNode left;<br>
\*     TreeNode right;<br>
\*     TreeNode(int x) { val = x; }<br>
\* }<br>
\*/<br>
class Solution {<br>
    public List<Integer> postorderTraversal(TreeNode root) {<br>
        Stack<TreeNode> stack = new Stack<>();<br>
        LinkedList<Integer> list = new LinkedList<>();<br>
        while (root != null || !stack.isEmpty()) {<br>
            while(root != null) {<br>
                stack.push(root);<br>
                list.addFirst(root.val);<br>
                root = root.right;<br>
            }<br>
            root = stack.pop().left; <br>
        }<br>
        return list;<br>
    }<br>
}<br>
