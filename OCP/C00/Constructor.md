# Part I C08

Constructor method can not have return type, not even void.

```java
public class Bunny {
	public bunny() { }      // DOES NOT COMPILE
  // Return type for the method is missing
  public void Bunny () {} // DOES NOT COMPILE
  // This method has a constructor name
}
```

Default constructor ist added when a class is declared without any contructors. it is also called no-argument construcor.

private constructor is useful when a class only has static methods or the developer wants to have full controll of all calls to create new instances of the class.

if it apears, this() and super() (with or without argument) must be the first statement in the constructor.

-   [ ] Order of Initialization