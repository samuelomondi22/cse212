**Tree**

Tree have a parent child relationship between items. It is like looking at a tree upside down with the root being the mother of everything. That is what we call a root node. Other parts connected to the root node are also nodes but more precisely a leaf. 

- ***Binary Tree***
It is a node with a maximum of two children. 

<img src="/binary.jpg">

- ***binary search tress***
More of a structural binary tree. All the nodes in the left sub-tree are less than or equal to the value of that node. Also, all the nodes in the right sub-tree of this node are greater than that of the parent node.

<img src="/bst.png">

Needful operations required for a BST are insert and display even though they need to maintain that BST remains with it's structure.

1. Inserting into BST.
<p>This operation requires recursion. Recursion is when the program keeps calling itself until a condition is met. We need this to find the path to the maximum and minimum value. This requires a performance of O(n) taking into consideration that the tree is not balanced but if the tree happens to be balanced the performance required would be O(1) as you could just cut the tree in half.</p>

<img src="/path.png">

The nodes are to be stored in a specific way for insertion to happen smoothly. Left side will hold less value than its own while the right holds the greater values.
Starting with a node of 5 as the root node to add a second value you have to compare with the root node. Since 5 is greater than 3 then:

<img src="/ex1.jpg">

```
def insert(self, data): 
    node = Node(data) 
    if self.root_node is None: 
            self.root_node = node 
    else:
        current = self.root_node 
        parent = None 
        while True: 
        parent = current
        if node.data < current.data:             
            current = current.left_child             
        if current is None:                 
            parent.left_child = node                 
            return 
```

2. Display
<p>We traverse when we want to display. The traverse will visit the each node from smallest to largest. It has a O(n) performance.</p>

```
"""
Helps in getting the next item
"""
def __iter__(self):
	yield from self._traverse_forward(self.root)  

def _traverse_forward(self, node):
	if node is not None:
    """
    yield provides the next value for the loop allowing the function to start back where it left off when 
    __iter__ is called again
    """
		yield from self._traverse_forward(node.left)
		yield node.data
		yield from self._traverse_forward(node.right)
```

**Example**
This code shows insertion within a tree. 
```
def insert(self, data):
	if self.root is None:
		self.root = BST.Node(data)
	else:
		self._insert(data, self.root)  # Start at the root

def _insert(self, data, node):
	if data < node.data:
		# The data belongs on the left side.
		if node.left is None:
			# We found an empty spot
			node.left = BST.Node(data)
		else:
			# Need to keep looking.  Call _insert
			# recursively on the left subtree.
			self._insert(data, node.left)
	elif data >= node.data:
		# The data belongs on the right side.
		if node.right is None:
			# We found an empty spot
			node.right = BST.Node(data)
		else:
			# Need to keep looking.  Call _insert
			# recursively on the right subtree.
			self._insert(data, node.right)
```

**Problem**
Using this example to insert in the node by comparing the left and right subtree.

When done , take a look at the [solution](/3-tree.py).