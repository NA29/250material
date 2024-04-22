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
store the min key in temp
remove the last leaf and store key in root
set the current node to the root

while the current key is greater than at least one of its children, we swap the current node with its child (smallest out of the two) and set the current node to the child. the while loop makes it "recursive"

return the value of the deleted node stored in temp originally


![[Pasted image 20240422014329.png]]

each depth at a time

parent index = child / 2

left child = 2* parent
right child = 2* parent + 1

![[Pasted image 20240422014950.png]]

add implementation used list
update the size because we add 1 new element
while the size is greater than 1 (not only root) and the child is smaller than the parent, we swap the child and the parent
	the child at this time is the current node so heap[\i] and the parent is heap[1/2]
update the size index (represents index of current node)

once we defined the add method, we can build a heap with the buildHeap method
![[Pasted image 20240422020250.png]]

==best case, array already a heap O(n)
worst case, (O(nlog(n)))==

remove min is similar for its implementation
![[Pasted image 20240422020956.png]]

![[Pasted image 20240422021249.png]]