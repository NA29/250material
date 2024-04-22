### Bubble Sort
Compare all adjacent elements, and swap if needed
		0 and 1
		1 and 2
		2 and 3
		3 and 4
		repeat
Iterate until sorted'

After the first iteration, the largest element is at the end of the list
	The smallest element can be anywhere except at the end of the list

! This means that after every iteration, we can stop comparing elements ONE STEP earlier (since every time the *new last element* will be the largest in this iteration)

![[Pasted image 20240411172131.png]]

We used the swapped signal to indicate when the list if finally sorted (break;)

Best case scenario, Big-omega N **OMEGA(N)**, list already sorted

Worst case scenario, **O(N^2)**, reverse order list

### Selection sort
We have two groups, sorted and unsorted
![[Pasted image 20240411181858.png]]

At every iteration, we find the smallest number, swap it with the first index (that index is not part of the sorted group)

The N-1th iteration is useless, because all the items will already be sorted
![[Pasted image 20240411182118.png]]
We are holding the minimum at every iteration in `min`
`min` is set to `i` at the beginning of each iteration

Best case and worst case will always be `O(N)`, unlike bubble sort

### Insertion sort
Similarly, we have two groups, sorted and unsorted
![[Pasted image 20240411182411.png]]

At every iteration, we take the first element of the unsorted group and insert it in its correct spot in the sorted list

The Nth iteration is needed because we still need to figure out where to insert the last element

Mechanism to insert is similar to ArrayList. We shift all elements ahead by one position to make a hole, and then we fill the hole
![[Pasted image 20240411191717.png]]

In the best case, where everything is sorted, `OMEGA(N)`

In the worst case, reverse order, `O(N^2)`

## SUMMARY
![[Pasted image 20240411191836.png]]![[Pasted image 20240417181253.png]]![[Pasted image 20240417181302.png]]