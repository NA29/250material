ex: ArrayList or LinkedList are generic classes with a type parameter

```
ArrayList<Integer> words = new ArrayList<Integer>();
ArrayList<Shape> myShapes = new Arraylist<Shape>();
```

When we create a class that can work for different types of items/types/etc

ex:
```
public class Cage<T> {
	private T occupant;
	public void lock(T p) {
		this.occupant = p;
		}
	public T peek() { ... }
	public void release() {
		this.occupant = null;
		}
}
```

If Cage is used for Dog of for Bird, it is always going to work

```
Common Type Parameter Names
	E - Elements
	K - Key
	N - Number
	T - Type
	V - Value
	S, U, V, ... - 2nd, 3rd, 4th types
```

We can filter (bound) the types that we accept 
```
public class Cage<T extends MonsterLike> {...}
```
We will only take MonsterLike objects

