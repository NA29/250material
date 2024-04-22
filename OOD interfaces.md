Reminder on abstract methods
```
	public abstract double getArea() {
	}
```
Every subclass must either override the abstract method or declare it itself as abstract

**Interfaces** tell what a class must do without implementations
```
public interface myInterface {
	public void methods
}
```
```
public interface MonsterLike {
	public int spook();
	public void runAway();
}
```
Interfaces are implicitly abstract -> no need to specify
Methods are by default public and abstract
Fields are by default public static and final
! Not the same as abstract class since it is not a class - similar functionality but not a class, tells the class what to do

To implement interface we need to *implement*
```
public class Dragon implements MonsterLike {
	public int spook();
	public void runAway();
}
```

In the same way as abstract classes, interfaces cannot be instantiated
```
We cannot do

MonseterLike m = new MonsterLike();
```

Instead, make a class that implements an interface, then use an instance of that class/interface
```
publlic class Dragon implements MonsterLike {}

Dragon Orc = new Dragon();
MonsterLike dragon = new Dragon();
```

Interfaces need to be imported if they are not located in the same package
```
import packageName.InterfaceName;
```

An interface can extends another interface
If a class implements an interface but does not implement all the methods in the interface, it must be declared abstract

! A class can extend at most one class (problem if two super-classes have implemented methods with the same signature, we don't know which one to use)

An interface can implement multiple interfaces (since they do not contain implementations, there is no problem even if they have the same signature)

REMINDER: a single subclass  extends exactly one superclass, a class can implement multiple interfaces, and an interface can extend more than one interface

```
public class Dragon extends Enemy implements MonsterLike, FireBreather {}
```


| Abstract class                                                                                                     | Interface                                                    |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------ |
| Not all methods need to be abstract                                                                                | All methods are abstract                                     |
| Abstract keyword is used to declared abstract class                                                                | Implicitly abstract                                          |
| Can contain implemented methods as well as instance variables                                                      | No method can be implemented, only constants can be declared |
| USED WHEN some general methods should be implemented and specific behaviour should be implemented by child classes | USED WHEN all properties should be implemented               |
