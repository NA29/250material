![[22 - Heaps.pdf]]
TLDR:
Priority queue
	Add an element
	Remove element with lowest priority
	add(key)
	removeMin()

Heaps are complete binary trees![[Pasted image 20240422011207.png]]

Filled from as left as possible
Min heap (like in the image)
Max heap: parents greater than children

If we wanna add c, we add from left to right, so next to the m![[Pasted image 20240422011330.png]]
however it destroys the heap property

we need to heapify, so transform it back into a heap 

#### adding
![[Pasted image 20240422011441.png]]

cur is the new node that is created
we set the key of the new node to the parameter of the method
if its an empty tree we set the root to the new node
while were not at the root and while the current node is smaller than the parent, we swap the current node with the parent
we set the current node to the parent because it is this node that we chose to add

when we remove min, we swap the root withthe last element added, then swap the last element added (now situated at the root, with its smallest child, recursively)

![[Pasted image 20240422012420.png]]
