# interview_questions
A mix of questions that are asked in technical interviews.


## What is the difference between an abstract class and an interface?

An abstract class is a class that cannot be instantiated, but can contain both abstract and concrete methods. An abstract method is a method that is declared, but does not have an implementation. This means that subclasses of the abstract class must implement the abstract methods.

On the other hand, an interface is a special type of abstract class that can only contain abstract methods and constants. An interface cannot be instantiated, and a class must implement all of the methods declared in an interface in order to implement the interface.

One key difference between an abstract class and an interface is that a class can extend only one abstract class, but can implement multiple interfaces. This allows for greater flexibility in designing and implementing classes, and is one of the reasons why interfaces are often preferred over abstract classes.

Another important difference is that abstract classes can have instance variables, while interfaces cannot. This means that abstract classes can store state, while interfaces cannot.

Overall, the main difference between an abstract class and an interface is that an abstract class can contain both abstract and concrete methods, while an interface can only contain abstract methods.
