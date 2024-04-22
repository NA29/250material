! Iterator is a Java interface

```
public interface Iterator<E> {
	boolean hasNext();
	E next();
}
```

! Iterable as well

```
public interface Iterable<E> {
	public Iterator<E> iterator();
}
```

iterator() method returns an object of type Iterator which can be used to iterate through the elements of this instance

A class implementing Iterable needs to implement iterator() method

![[Pasted image 20240411024115.png]]

We usually keep it a private inner class
![[Pasted image 20240411024253.png]]

**FOR EACH LOOP**
![[Pasted image 20240411024442.png]]
![[Pasted image 20240411024808.png]]

For each loop is faster, O(N)