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

if it apears, this() and super() (with or without argument) must be the first statement in the constructor. And thus there can be only one call to this() or super() in any constructor.

If the parent class has more than one constructor, the child class may use any valid parent constructor in its definition, as long as the appropriate input paramters to the parent constructor are provided.

Java compiler inserts a call to the no-argument constructor super() if you do not explicitly call this() or super() as the first line of a constructor.

[x] Order of Initialization
-   static variables and static initializers in order
-   instance variables and instance initializers in order
-  main()
-   constructors

final variables can be assigned in the line in which they are declared or in an instance initializer or in constructor.
By the time the constructor completes, all final instance variables must be assigned a value. Java compiler won't allow any situation, in which a final instance variable is not assigned. For example, a constructor that doesn't perform assignment to all final instance variables which are not already assigned by in line assignment or by instance initializer won't compile.

Initialize Class X
1. If there is a superclass Y of X, then initialize class Y first.
2. Process all static variable declarations in the order they appear in the class.
3. Process all static initializers in the order the appear in the class.

The most important rule with class initialization is that it happens at most once for each class.

Initialize Instance of Class X

1. If there is a superclass Y of X, then initialize the instance of Y first.
2. Process all instance variable declarations in the order they appear in the class.
3. Process all instance initializers in the order they appear in the class.
4. Initialize the constructor including any overloaded constructors referenced with this().

1. The first statement of every constructor is a call to an overloaded constructor via this(), or a direct parent constructor via super()
2. If the first statement of a constructor is not a call to this() or super(), then the compiler will insert a no-argument super() as the first statement of the constructor.
3. Calling this() and super() after the first statement of a constructor results in a compiler error.
4. If the parent class doesn't have a no-argument constructor, then every constructor in the child class must start with an explicit this() or super() constructor call. (Implicit super constructor is undefined)
5. If the parent class doesn't have a no-argument constructor and the child doesn't define any constructors, then the child class will not compile. (Implicit super constructor is undefined for default constructor)
6. If a class only defines private constructors, then it cannot be extended by a top-level class. (can be extended by inner class)
7. All final instance variables must be assigned a value exactly once by the end of the constructor. Any final instance variables not assigned a value will be reported as a compiler error on the line the constrctor is declared.