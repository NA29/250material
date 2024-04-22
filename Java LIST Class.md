declaration of List
```
public interface List<E> extends Collection<E> {
	boolean add (E e);
	void add(int i, E e);
	boolean isEmpty();
	E get(int i);
	E remove(int i);
	int size();

}
```

ArrayList implements List
	All of the methods inherited from List are implemented in ArrayList

LinkedList implements List

In both cases, all the methods AND MORE are implemented

![[Pasted image 20240411022731.png]]

```
In this case, if we create varaibles of List<String>; we can assign to them any value referencing to instances of ArrayList<String> or LinkedList<String> 
```


```
public void sort(List<String> list) {...}
```
When an object of type List is required, any instance of classes that implement List can be used
We can pass ArrayList or LinkedList as a paremeter for sort()

