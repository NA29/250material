### Principle: split the list into two halves, sort each half recursively, merge the sorted half maintaining the order

![[Pasted image 20240420193709.png]]**When size = 1, it means that the list is sorted, because it cannot be split into smaller lists to sort**

When merging, we compare the elements of the two new sorted lists to determine the order of the elements in the final list. When one sub list has no more element, we simply copy the remaining elements of the other list to the end of the final list. 

#### Dividing
![[Pasted image 20240420203354.png]]
as mentioned, the middle is the max index- min index divided by 2, so list.size() -1 divided by 2

We use the getElements(start, finish) method to create the sublists, simple index logic


#### Merging
![[Pasted image 20240420203625.png]]
We start by creating an empty list, that we are going to add elements to later on

While both lists are NOT empty, we proceed with the comparison logic
- If the first element of a list is smaller/greater than the first element of the other list, we addlast(list.removeFirst())
	- That way, the smallest element is added to the final list, while being deleted form the sub list
When one of the lists is empty, we check which one is not empty and add all the remaining elements to the final list, in a "check if not empty" while loop

#### Finalized mergesort implementing the previous method
![[Pasted image 20240420204137.png]]
If the list contains only one element, then its the base case, no need to sort, returns list directly

Elsewise, 
- Find middle as shown above
- Create sub lists

- Recursive search, splitting the list in half until size = 1 and merging upwards  until we obtain two sorted sub lists

- Merge the two sub lists (same as what has been done in the recursive sorting step, but one last time for the two main sub lists)

==O(nlog(n)) always

### Recurrence solving using back substitution

	T(1) = a
	T(n) = b + c * n + 2T(n/2)
			b for idk what
			c * n for getElements and merge (depends on the num of elements to iterate through and 2T(n/2) for the recursive part on half of the list)

	T(n) = c * n + 2(c * n/2  + 2T(n/4))
	T(n) = 2c * n + 4(c * n/4 * 2T(n/8))
	T(n) = 3c * n + 8T(n/8)

	T(n) = kcn + 2^k * T(n/2^k)

		assuming k = log_2(n) to create T(1)
		
	T(n) = cnlog_2(n) + 2^log_2(n) * T(1)

==THETA(nlog_n)

==nlog_2(n) is much closer to n than to n^2
