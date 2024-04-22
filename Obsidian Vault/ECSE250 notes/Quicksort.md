![[Pasted image 20240420213129.png]]
We choose a pivot
- Pick first element or
- Pick last element or
- Pick median element or
- Pick random element

Let's pick the last element

#### Method
1. Pick the last element
2. Set a wall on the left of the list (assume list is horizontally presented)
3. Go through all the elements of the list that are not the pivot
	1. If smaller than pivot, move the wall (separation) to the right by 1 index and place the element just behind the wall
	   **Swapping the element on the left of the wall AFTER the +1 idx with the compared element**
	2. Otherwise, do nothing
4. Move the pivot to the right of the wall
   **Swap the pivot with the element currently on the right of the wall**
5. Quicksort on left part of the wall and then on right part (recursive step)

#### Functions needed for Quicksort
- swap()
- A way to refer to parts of the list
- placeAndDivide()
	- Places pivot in correct position and moves elements around so that lower elements are to the left and greater elements are to the right (left and right unsorted)
- Implementation of Quicksort
	- Pick a pivot
	- placeAndDivide
	- quickSort left part **recursive**
	- quickSort right part **recursive**

![[Pasted image 20240420223358.png]]
If the left index is greater than the right, just like in binary search, that means that the sorting process is finished

Elsewise, get the pivot, separate the elements to the left and to the right of the pivot
Recursive call to sort left and right parts of the list

==Best case : pivot always in the middle
	T(n) = cn + 2T(n/2)
	Running time: OMEGA(nlog_2(n))

==Worst case: pivot always smaller or larger than the elements (list already sorted for eg.)
	T(n) = cn + T(n-1)
	Running time: O(n^2)

We can improve the running time by choosing the pivot better

![[Pasted image 20240421001805.png]]
Summary of merge sort vs quick sort