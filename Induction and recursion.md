### Proof by mathematical induction
- Base case
- Inductive step
- Conclusion

Base case
- Verify that P(n0) is true

Inductive step
- Assume P(k) is true and prove that P(k+1) is true

Conclusion
- P(n) is true

#### Example
Prove that **For all n>=3, 2n + 1 < 2^n**

- Base case
	- n = 3
	- 2\*3+1 = 7
	- 2^3 = 8
	- 2\*3 + 1 < 2^3
	- True, case proven
- Inductive step
	- Assume 2 \* k +1 < 2^k
	- Prove 2 \* (k+1) < 2^(k+1)
	- True
- Therefore conclusion true
	==same as MATH240

Recursion
**same as Python, function calls itself, if statement for condition and else statement with recursive call**
![[Pasted image 20240418204050.png]]Condition in if statement prints GO! if met
Otherwise else statement is executed (until if is satisfied)


### Recursive methods
- Base case
	- Terminating scenario(s) that do not use recursion
- Recursive step
	- Determines how to produce an answer from simpler cases
**IF THE BASE CASE IS MISSING, THE METHOD WILL NEVER END

#### Factorial example
```
public static int factorial (int n) {
	if (n == 0) { 
		return 1;
		}
	else {
		return n * factorial(n-1);
		}
}
```
We multiply **n** by **n-1** until n == 0


#### Fibonnaci numbers example
```
fibonnaci(n) {
	if ((n==0) || (n==1)) {
		return n;	
	}
	return fibonnaci(n-1) + fibonnaci(n-2);
}
```
Since every term of the Fibonnaci sequence is equal to itself minus 1 + itself minus 2


#### Power of **n** example
If we were to write the method iteratively instead of recursively, we would make a for loop iterating through 1 to n of result = x * result

Recursively
```
public static int power(x, n) {
	if (n==0) {
		return 1;
		}
	else {
		return x * power(x, n-1);
		}
}
```
Running time O(n)


### Computational complexity again
- Best case scenario => O(N)
- Worst case scenario OMEGA(N)

If the algorithm has both O(N) and OMEGA(N), then it is called THETA(N)
**Both have to be the same


#### Back substitution
This method is used to find the time complexity by plugging a common value instead of the long terms of a recursive series

For example, take the power of n example:
```
T(1) = b
T(n) = c + T(n-1)
T(n) = c + c + T(n-2)
T(n) = c + c + c + T(n-3)
T(n) = 3c + T(n-3)
T(n) = kc + T(n-k)
T(n) = (n-1) + T(n - (n - 1))
T(n) = (n-1) + T(1)
T(n) = (n-1) + b

As we can see, after the simplification, the formula become O(N)
Since it is also OMEGA(N), we can say it is THETA(N)
```

==T is the time complexity, not the result, we are calculating the time here

#### Sorting a linked list example
![[Pasted image 20240418214602.png]]
In this method, we remove the smallest element and add in in front of the list. Recursion is used after removing the minimum to perform operations on the new size =- 1 list. At the end, the minimum members are added to the list from the bottom of the recursion upwards

```
T(1) = a //which is the base case
T(N) = b + c * n + T(n-1)  //which is the recursive step

T(n) = b + cn + T(n-1)
T(n) = 2b + cn + c(n-1) + T(n-2)
T(n) = 3b + cn + c(n-1) + c(n-2) + T(n-3)
becomes
T(n) = b(k + 1) + c(n + (n-1) + (n-2) + ... + (n-k)) + T(1)
T(n) = bn + 1/2 cn^2 + 1/2 cn - c + a
	when k = n - 2

RUNNING TIME = THETA(n^2)

**b(k + 1) because of the initial b, and the b used for each term
** - c because T(2) = b + 2c + T(1) and T(1) = a
** need to know that the sum of n + (n+1) + (n+2) ...= n(n+1)/2
```
==Notice how we have a term for each step of the recursive method


### Tower of Hanoi example![[Pasted image 20240418232828.png]]
