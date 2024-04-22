#### Used to define an ordering of objects of USER-DEFINED class
#### Part of java.lang and contains only compareTo(Object)

	public interface Comparable<T> {
		int compareTo(T o);
		}

*Some methods from Java claseses, eg. sort() from Arrays, use compareTo() in their implementation*

*In fact, "Character, Integer, Float, Double, etc..." all implement Comparable<\T>*

==We cannot compare objects of these classes using the < > operators. Instead, use compareTo()

#### How to implement Comparable
1. Add `implements Comparable` in the definition of the class
2. Implement `compareTo()` inside the class

![[Pasted image 20240421002344.png]]

![[Pasted image 20240421002425.png]]

Normally, `o1.compareTo(o2) == 0` has the same result as `o1.equals(o2)`

#### Example of implementation of compareTo() and equals() for circles
![[Pasted image 20240421002654.png]]
- We add `implements Comparable<Circle>` in the head
- We compare 'this' to the parameter
- We output -1, 0, or 1
- In equals method, we use instance of && to additionally check the type
- We use epsilon method because of uncertainty (?)

==When we are comparing more complex objects which have multiple characteristics, we can't simply compare one characteristic and call it a day. Ideally, we would have an implementation of compareTo() in each subclass that we are comparing. In the main class (eg. Orc), we would use the specific implementations of the compareTo method.

![[Pasted image 20240421003657.png]]
**We see that the String, Integer, Weapon classes all have implementations of compareTo)**