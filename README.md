# avl_tree

An AVL tree is a type of binary search tree (BST) that maintains balance by ensuring the height difference between the left and right subtrees (called the balance factor) of any node is at most 1. This balancing is achieved through rotations during insertion and deletion operations, which ensures that the tree remains balanced, providing O(log n) time complexity for search, insertion, and deletion operations.


Height of a Node:
The height of a node in a tree is the number of edges on the longest path from the node to a leaf. If a node is a leaf, its height is 0.
h(node) = max(h(node.left), h(node.right)) + 1
If the node is None, the height is considered -1.

Balance Factor:
The balance factor of a node is defined as the difference in height between its left and right subtrees:
BF(node) = h(node.left) - h(node.right)
For an AVL tree, the balance factor for each node must be -1, 0, or 1. If the balance factor goes outside this range, the tree needs to be rebalanced.

Rotations:
Single Right Rotation (LL Rotation):
Applied when a node becomes unbalanced due to an insertion in the left subtree of its left child.
Example:
    y           x
   /           / \
  x    ==>    z   y
 /
z

Single Left Rotation (RR Rotation):
Applied when a node becomes unbalanced due to an insertion in the right subtree of its right child.

Example:
x                y
 \              / \
  y    ==>     x   z
   \
    z

Left-Right Rotation (LR Rotation):
Applied when a node becomes unbalanced due to an insertion in the right subtree of its left child.
It is a combination of a left rotation followed by a right rotation.

Example:
   y             y           z
  /             /           / \
 x     ==>     z     ==>   x   y
  \           /
   z         x
   
Right-Left Rotation (RL Rotation):
Applied when a node becomes unbalanced due to an insertion in the left subtree of its right child.
It is a combination of a right rotation followed by a left rotation.

Example:
x              x             z
 \              \           / \
  y     ==>      z   ==>   x   y
 /                \
z                  y


Insertion in AVL Tree
BST Insertion:
Insert the node as in a regular binary search tree.
After insertion, update the height of the node.

Balancing the Tree:
After insertion, check the balance factor of each node from the inserted node back up to the root.
If a node becomes unbalanced:
LL Case: Perform a right rotation.
RR Case: Perform a left rotation.
LR Case: Perform a left rotation on the left child, followed by a right rotation on the node.
RL Case: Perform a right rotation on the right child, followed by a left rotation on the node.

Deletion in AVL Tree
BST Deletion:
Remove the node as in a regular binary search tree.
After deletion, update the height of the nodes affected.

Balancing the Tree:
Similar to insertion, check the balance factor of each node from the deleted node's parent back up to the root.
Apply the appropriate rotations to balance the tree.


Height of Node n:
h(n) = max(h(n.left), h(n.right)) + 1

Balance Factor of Node n:
BF(n) = h(n.left) - h(n.right)

Conditions for Rotation:
LL Case: BF(n) > 1 and BF(n.left) >= 0
RR Case: BF(n) < -1 and BF(n.right) <= 0
LR Case: BF(n) > 1 and BF(n.left) < 0
RL Case: BF(n) < -1 and BF(n.right) > 0
