# Trees
**Terminology**
- Node - A Tree node is a component which may contain its own values, and references to other nodes
- Root - The root is the node at the beginning of the tree
- K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
- Left - A reference to one child node, in a binary tree
- Right - A reference to the other child node, in a binary tree
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not have any children
- Height - The height of a tree is the number of edges from the root to the furthest leaf

**Traversals**
raversing a tree allows us to search for a node, print out the contents of a tree, and much more! 

*There are two categories of traversals when it comes to trees:*
1. Depth First
2. Breadth First

## Depth first
Where we prioritize going through the depth (height) of the tree first

The most common way to traverse through a tree is to use recursion. With these traversals, we rely on the call stack to navigate back up the tree when we have reached the end of a sub-path.

*Three methods for depth first traversal:*

1. Pre-order: root >> left >> right
2. In-order: left >> root >> right
3. Post-order: left >> right >> root

**Pre-order**

- When we call preOrder for the first time, the root will be added to the call stack
- Next, we start reading our preOrder function’s code from top to bottom.
- Then, our next block of code instructs us to check if our root has a left node set. If the root does, we will then send the left node to our preOrder method recursively. 
- This process continues until we reach a leaf node.

ALGORITHM preOrder(root)
    // INPUT <-- root node
    // OUTPUT <-- pre-order output of tree node's values

        OUTPUT <-- root.value

        if root.left is not Null
            preOrder(root.left)

        if root.right is not NULL
            preOrder(root.right)

**In-order**
ALGORITHM inOrder(root)
    // INPUT <-- root node
    // OUTPUT <-- in-order output of tree node's values

        if root.left is not NULL
            inOrder(root.left)

        OUTPUT <-- root.value

        if root.right is not NULL
            inOrder(root.right)

**Post-order**
ALGORITHM postOrder(root)
    // INPUT <-- root node
    // OUTPUT <-- post-order output of tree node's values

        if root.left is not NULL
            postOrder(root.left)

        if root.right is not NULL
            postOrder(root.right)

        OUTPUT <-- root.value

# Breadth-first
Breadth first traversal iterates through the tree by going through each level of the tree node-by-node

Breadth first traversal uses a queue (instead of the call stack via recursion) to traverse the width/breadth of the tree. Let’s break down the process.

ALGORITHM breadthFirst(root)
    // INPUT  <-- root node
    // OUTPUT <-- front node of queue to console

    Queue breadth <-- new Queue()
    breadth.enqueue(root)

    while ! breadth.is_empty()
        node front = breadth.dequeue()
        OUTPUT <-- front.value

        if front.left is not NULL
        breadth.enqueue(front.left)

        if front.right is not NULL
        breadth.enqueue(front.right)

# Binary Tree Vs K-ary Trees
Binary Trees restrict the number of children to two (hence our left and right children).

If Nodes are able have more than 2 child nodes, we call the tree that contains them a K-ary Tree. In this type of tree we use K to refer to the maximum number of children that each Node is able to have.

**Breadth First Traversal**
We are still pushing nodes into a queue, but we are now moving down a list of children of length k, instead of checking for the presence of a left and a right child.

ALGORITHM breadthFirst(root)
    // INPUT  <-- root node
    // OUTPUT <-- front node of queue to console

    Queue breadth <-- new Queue()
    breadth.enqueue(root)

    while ! breadth.is_empty()
        node front = breadth.dequeue()
        OUTPUT <-- front.value

        for child in front.children
            breadth.enqueue(child)


*Adding a node*
It really doesn’t matter where a new node gets placed.
One strategy for adding a new node to a binary tree is to fill all “child” spots from the top down. During the traversal, we find the first node that does not have all its children filled, and insert the new node as a child. We fill the child slots from left to right.

*Big O* 
- Inserting a new node is O(n)
- Searching for a specific node is O(n)
- Node insertion using breadth first insertion will be O(w), where w is the largest width of the tree.
- A “perfect” binary tree is one where every non-leaf node has exactly two children. The maximum width for a perfect binary tree, is 2^(h-1), where h is the height of the tree. Height can be calculated as log n, where n is the number of nodes.

## Binary Search Trees

A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

**Searching a BST**

Searching a BST can be done quickly, because all you do is compare the node you are searching for against the root of the tree or sub-tree. If the value is smaller, you only traverse the left side. If the value is larger, you only traverse the right side.

**Big o**

The Big O time complexity of a Binary Search Tree’s insertion and search operations is O(h), or O(height). In the worst case, we will have to search all the way down to a leaf, which will require searching through as many nodes as the tree is tall. In a balanced (or “perfect”) tree, the height of the tree is log(n). In an unbalanced tree, the worst case height of the tree is n.

The Big O space complexity of a BST search would be O(1). During a search, we are not allocating any additional space.