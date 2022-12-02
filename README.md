# interview_questions
A mix of questions that are asked in technical interviews.


## What is the difference between an abstract class and an interface?

An abstract class is a class that cannot be instantiated, but can contain both abstract and concrete methods. An abstract method is a method that is declared, but does not have an implementation. This means that subclasses of the abstract class must implement the abstract methods.

On the other hand, an interface is a special type of abstract class that can only contain abstract methods and constants. An interface cannot be instantiated, and a class must implement all of the methods declared in an interface in order to implement the interface.

One key difference between an abstract class and an interface is that a class can extend only one abstract class, but can implement multiple interfaces. This allows for greater flexibility in designing and implementing classes, and is one of the reasons why interfaces are often preferred over abstract classes.

Another important difference is that abstract classes can have instance variables, while interfaces cannot. This means that abstract classes can store state, while interfaces cannot.

Overall, the main difference between an abstract class and an interface is that an abstract class can contain both abstract and concrete methods, while an interface can only contain abstract methods.

## What is the GIL in python?
The Global Interpreter Lock (GIL) in the CPython implementation of Python prevents multiple native threads from executing Python bytecodes at the same time. This means that only one thread can execute Python code at a given time, even if the computer has multiple CPUs or cores.

This can be a limiting factor in the performance of multithreaded Python programs, since it prevents multiple threads from executing simultaneously. In a sense, it avoids "real" parallel programming, because it ensures that only one thread can run at a time, regardless of the number of available CPU cores.

There are a few reasons why the GIL is in place in CPython. One reason is that the GIL makes it easier to implement Python's dynamic, interpreted nature. Since the GIL ensures that only one thread can execute Python code at a time, it simplifies the task of the interpreter, which does not have to worry about concurrency issues.

Another reason for the GIL is that many of the core data types in Python are not thread-safe. This means that if multiple threads were allowed to execute Python code simultaneously, there could be race conditions or other concurrency issues that could lead to incorrect or unpredictable behavior. The GIL prevents these issues by ensuring that only one thread can execute Python code at a time.

Overall, the GIL in Python prevents "real" parallel programming in multithreaded programs by ensuring that only one thread can execute Python code at a time. This simplifies the implementation of the interpreter and helps to prevent concurrency issues, but can also limit the performance of multithreaded Python programs.

## Explain what is MRO in Python and how it works.
MRO stands for Method Resolution Order. In Python, the MRO is the order in which superclasses are searched for method resolution when a method is called on a class that derives from multiple superclasses.

In Python, classes can have multiple superclasses, allowing for a form of multiple inheritance. However, this can lead to ambiguities when a method is called on a derived class, because the derived class may have multiple superclasses that define the same method.

To resolve this ambiguity, Python uses the MRO to determine the order in which superclasses are searched for a method when it is called on a derived class. The MRO is determined using a depth-first, left-to-right search, where the leftmost superclass is searched first, and then the search continues in a left-to-right order through the remaining superclasses.

For example, consider the following class hierarchy:
```python
class A:
    def foo(self):
        print("A.foo")

class B(A):
    pass

class C(A):
    def foo(self):
        print("C.foo")

class D(B, C):
    pass
```

In this example, class D derives from both class B and class C. If we call the foo method on an instance of class D, the MRO determines that the method should be resolved using the definition from class C, because class C is searched before class A in the MRO for class D.

The MRO for a class can be accessed using the mro method on the class. For example, we can print the MRO for class D as follows:
```python
print(D.mro()) # [D, B, C, A, object]
```

This shows the order in which superclasses are searched when a method is called on an instance of class D.

Overall, the MRO is a mechanism in Python that determines the order in which superclasses are searched when a method is called on a derived class. This allows Python to resolve ambiguities when multiple superclasses define the same method.
