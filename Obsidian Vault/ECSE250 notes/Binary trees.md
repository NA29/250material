### EACH NODE HAS AT MOST 2 CHILDREN

## Binary search trees
### ELEMENTS ARE COMPARABLE AND UNIQUE
### ALL DESCENDENTS ON THE LEFT ARE SMALLER THAN THE NODE AND ALL DESCENDENTS ON THE RIGHT ARE GREATER
#### The comparison is based on node key (.element)

```
class BTree<T> {
	BTNode<T> root;

	private class BTNode<T> {
		T element;
		BTNode<T> leftchild;
		BTNode<T> rightchild;
		}
}
```

==the maximum number of nodes in a binary tree of height *h* is 2^(h+1) - 1==
==the minimum number of nodes is h + 1 (ever layer + root)

![[Pasted image 20240421122142.png]]
**The difference is instead of for looping, we call recursively twice, for left and right**

![[Pasted image 20240421122236.png]]
New order. ==Left, visit root, right==

![[Pasted image 20240421122433.png]]

## Binary search trees

```
class BSTNode<K> {
	K key;
	BSTNode<K> leftchild;
	BSTNode<K> rightchild;
}
```

**In order traversal visits the nodes in their natural ascending order (left < middle < right always)**
- No sorting required

#### findMin()
- Only need to find leftmost node

![[Pasted image 20240421124157.png]]
Find left node until no more left node

==BEST CASE => OMEGA(1)==
==WORST CASE => O(n)

#### findMax()
- Only need to find rightmost node

![[Pasted image 20240421124344.png]]

==BEST CASE => OMEGA(1)==
==WORST CASE => O(n)==

#### find(key)
- Returns node with key

![[Pasted image 20240421124554.png]]
If node is key, return directly, is target is smaller than node, look left, otherwise look right

==BEST CASE => OMEGA(1)==
==WORST CASE => O(n)==

#### add(key)
- If empty, add root
- Otherwise, attach to a leaf node

![[Pasted image 20240421124940.png]]
- If empty create root
- If smaller than node, add it to the left node (we use = because method returns final node)
-  If greater, add it to right node
- Return the final node that the key has been appended to

==BEST CASE => OMEGA(1)==
==WORST CASE => O(n)==

#### remove(key)
- Remove the node
- 3 cases
	1. No left subtree
		Replace with the right subtree
	2. No right subtree
		Replace with left
	3. Both left and right subtree
		Find the closest element (smallest in right, largest in left)

![[Pasted image 20240421134425.png]]
![[Pasted image 20240421134432.png]]

![[Pasted image 20240421134635.png]]
- If empty, null
- If the key is <> than node, recursive call on right or left node
- When equal, check if one of the left/right is absent, then replace with the other one
- Otherwise third case -> find the min node in right subtree and get the key
	- Replace the node's key with the new min key
	- Remove the min node since it has been moved to the top relatively

==BEST CASE => OMEGA(1)==
==WORST CASE => O(n)==

#### Balanced tree
A binary tree is called _balanced_ if every leaf node is not more than a certain distance away from the root than any other leaf.

![[Pasted image 20240421135603.png]]
For the last tree to be balanced, it should have a child to the right of the root node
(Height 2 - Height 0 does not work currently)

![[Pasted image 20240421135720.png]]

