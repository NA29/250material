### Finding a given element in a list
#### Solution: go thru all the elements in the list and check whether the element is there (linear search)

#### We can do it faster with binary search

### Binary search (finding element in a sorted list)
- Inputs:
	- A sorted list
	- The element we're looking for (key)
- Compare with middle of the list
	- If less than middle, only search left half of the list
	- Right side if greater
	- If equal, return index
	- If element not present in the list, return -1
==every comparison discards half of the list

Steps
- Compute mid
	- mid = (left + right) / 2  ==talking about indices of the items
	- truncate down if decimal number

	- Second time, one of the borders doesnt change, the other one is mid +- 1
	- After every comparison, we update right or left depending on which side we discard
	- **whenever right<left, we return -1, this means that no element has been found inside the list
![[Pasted image 20240420192429.png]]
The if statement indicates that there are still elements that have not been looked through**
When left is not <= right, this means that the direction has been flipped and that we should return -1, indicating unsuccessful search
Recurrence in the else statement
*We search again within the smaller list if nothing has been found*

==The best case happens when the element is at the middle of the list -> O(1)
The worst case happens when the element cannot be found in the list
	At each recursive call, we cut the size down to approx. half
	Roughly O(logn)


	T(1) = b
	T(n) = c + T(n/2)
	Generally we would write T(n) = c + T(floor(n/2))

	**Using back substitution to solve the recurrence**

	T(n) = c + T(n/2)
	T(n) = c + c + T(n/4) 
	T(n) = c + c + c = T(n/8)
	T(n) = kc + T(n/2^k)

	T(n) = c * log_2(n) + T(1) ; when k = log_2(n)
	T(n) = c * log_2(n) + b
==O(log_2(n)) or more generally O(logn) 

