# Trees

Trees are hierarchical data structures composed of nodes connected by edges. Each node in a tree has a value and may have zero or more child nodes. Trees are widely used in computer science for representing hierarchical relationships, such as file systems, organizational structures, and data representations.

## Basics of Trees

- **Root:** The topmost node in a tree.
- **Parent and Child Nodes:** Nodes in a tree are connected in a parent-child relationship, where a parent node can have one or more child nodes.
- **Leaf Nodes:** Nodes without any children are called leaf nodes.
- **Depth:** The depth of a node is the number of edges from the root to that node.
- **Height:** The height of a tree is the maximum depth of any node in the tree.

Here's an example of a simple binary tree:

```
       1
      / \
     2   3
    / \
   4   5
```

## Tree Traversal

Traversal refers to visiting all nodes of a tree in a specific order. There are several ways to traverse a tree:

- **Inorder Traversal:** Visit left subtree, then current node, then right subtree.
- **Preorder Traversal:** Visit current node, then left subtree, then right subtree.
- **Postorder Traversal:** Visit left subtree, then right subtree, then current node.

```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

# Example tree creation
root = TreeNode(1)
root.left = TreeNode(2)
root.right = TreeNode(3)
root.left.left = TreeNode(4)
root.left.right = TreeNode(5)

# Inorder traversal
def inorder_traversal(node):
    if node:
        inorder_traversal(node.left)
        print(node.value)
        inorder_traversal(node.right)

print("Inorder Traversal:")
inorder_traversal(root)

# Preorder traversal
def preorder_traversal(node):
    if node:
        print(node.value)
        preorder_traversal(node.left)
        preorder_traversal(node.right)

print("\nPreorder Traversal:")
preorder_traversal(root)

# Postorder traversal
def postorder_traversal(node):
    if node:
        postorder_traversal(node.left)
        postorder_traversal(node.right)
        print(node.value)

print("\nPostorder Traversal:")
postorder_traversal(root)
```

## Binary Search Trees (BST)

A Binary Search Tree is a special type of binary tree where the left subtree of a node contains only nodes with values lesser than the node's value, and the right subtree contains nodes with values greater than the node's value. This property enables efficient search, insertion, and deletion operations.

```python
class BinarySearchTree:
    def __init__(self):
        self.root = None

    def insert(self, value):
        self.root = self._insert(self.root, value)

    def _insert(self, node, value):
        if node is None:
            return TreeNode(value)
        if value < node.value:
            node.left = self._insert(node.left, value)
        elif value > node.value:
            node.right = self._insert(node.right, value)
        return node

    def search(self, value):
        return self._search(self.root, value)

    def _search(self, node, value):
        if node is None or node.value == value:
            return node
        if value < node.value:
            return self._search(node.left, value)
        else:
            return self._search(node.right, value)

# Example BST usage
bst = BinarySearchTree()
bst.insert(50)
bst.insert(30)
bst.insert(70)
bst.insert(20)
bst.insert(40)
bst.insert(60)
bst.insert(80)

search_result = bst.search(40)
if search_result:
    print(f"Value 40 found in BST.")
else:
    print(f"Value 40 not found in BST.")
```

## Applications of Trees

- **File Systems:** Representing directories and files.
- **Hierarchical Data:** Organizing hierarchical data such as organizational charts.
- **Binary Search Trees:** Efficiently storing and searching data in sorted order.

Understanding trees and their traversal algorithms is fundamental to many areas of computer science and programming.

## Example Problem: Counting Leaf Nodes

Let's solve a problem using trees. Given a binary tree, write a function to count the number of leaf nodes in the tree (i.e., nodes with no children).

```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

# Function to count leaf nodes
def count_leaf_nodes(node):
    if node is None:
        return 0
    if node.left is None and node.right is None:
        return 1
    return count_leaf_nodes(node.left) + count_leaf_nodes(node.right)

# Example tree creation
root = TreeNode(1)
root.left = TreeNode(2)
root.right = TreeNode(3)
root.left.left = TreeNode(4)
root.left.right = TreeNode(5)

leaf_count = count_leaf_nodes(root)
print(f"Number of leaf nodes: {leaf_count}")  # Outputs: Number of leaf nodes: 3
```

In this example, we recursively count the leaf nodes in a binary tree by checking if a node has no children (left and right are both None), and incrementing the count accordingly.

[Back to Welcome Page](0-welcome.md)
