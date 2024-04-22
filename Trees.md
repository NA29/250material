#### ArrayLists and Linked Lists are linear data structures
#### Trees are non-linear

![[Pasted image 20240421010712.png]]

### **Terminology**
- Root: top node in a tree (eg. object)
- Child: node directly connected to another node when moving ==AWAY== from the root
- Parent is """""" ==TOWARD== the root
- Every node except the root node is a child, and has ==EXACTLY== one parent
	- Meaning two nodes cannot lead to one common node
- Siblings are nodes which have the same parent
	- Although two nodes cannot lead to one node, one node can lead to two nodes
- Vertexes are nodes (elements of the tree)
- Directed edge is an ordered pair of nodes (v_i, v_j) *from, to*
Trees can be undirected or directed. If directed, the edges are either all pointing away from the root or all pointing towards the root

#### Edge directions
![[Pasted image 20240421011339.png]]
**Same thing as graphs in MATH240**

#### When edged are undirected, there is no way to define the root
Therefore, we have unrooted trees (who knows where the tree starts and ends)

==IF A TREE HAS n NODES, IT HAS n-1 EDGES  

#### Subtrees
If a tree has n > 0 nodes, at least one is the root
If a tree has n > 1 nodes, each non-root node (and its descendants) forms a subtree
![[Pasted image 20240421011849.png]]

### Creating a tree
Same as linked list, we create a data type for the node, then we implement the Tree type and assign a pointer to the root node

```
class TreeNode<T> {
	T element;
	ArrayList<TreeNode<T>> children;

	//optional
	TreeNode<T> parent;
}

class Tree<T> {
	TreeNode<T> root;

	private class TreeNode<T> {
	
		T element;
		ArrayList<TreeNode<T>> children;
		
		//optional
		TreeNode<T> parent;		
		}
}
```
- T element stores the actual data of the element in the node
- the ArrayList stores nodes, not elements. The nodes have a .element attribute tho
- Tree class initializes a root node
- **Declaring twice is useless, we only need to declare TreeNode<\T> once, inside Tree<\T> class**

#### An *internal node* is a node with at least one child (in-between)
#### A *leaf* is a node with no children (also external node, terminal node)

#### Path is a sequence of nodes (v1, v2, v3, ..., vk) with edges between

#### Length of a path is the number of edges (nodes - 1)

#### Node is *ancestor* if there is a path from v to w

#### The opposite is *descendent*

#### Depth of a node is the length from root to node

![[Pasted image 20240421013709.png]]
Recursive method to calculate depth. Tracing from parent to node and counting

#### Height is the maximum length of a path from *node* to *leaf*

![[Pasted image 20240421013833.png]]

### Preorder traversals

![[Pasted image 20240421024911.png]]

1. Visit the node (do something with it)
2. Preorder traversal of each subtree

```
pseudocode

preorder (root) {
	if (root not empty) {
		visit root
		for each child of root
			preorder ( child )     //recursive call
	}
}
```
**Preorder traversal -> visit the root before the children**
We assume that we iterate through children from left to right
![[Pasted image 20240421121006.png]]



### Postorder traversal
1. Postorder traversal of each subtree
2. Visit the node (do something with it)

```
pseudocode

postorder (root) {
	if (root not empty) {
		for each child of root
			postorder ( child )     //recursive call
		visit root
	}
}
```
This method visits the root AFTER the children, not before

We used postorder when dealing with tree height

![[Pasted image 20240421121529.png]]

