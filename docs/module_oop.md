# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?
R: In systems design, a fail-fast system is one which immediately reports any error and stops the execution of the program at different points in the execution, in order to avoid bigger failures later on.

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?
R: You have to pass through every single node until you get to the middle of it. (0(n/2))
More exactly you can create a while loop where you create 2 pointers a fast one and a slow one, giving the fast one the value of node.next.next and to slow on node.next, when the fast one reaches the end the slow one will be exactly on the middle.

#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?
R: Use array.sort on it then iterate until the 99th element and compare each element with the next one, until you find it. If the element is not found it means it’s the last one, and if you find it previously, you can just break the loop upon retrieval.

#### What is a linked list? How to find if a linked list has a loop?
R: -A linked list is a list of elements that are connected by reference to the next element.
-Traverse the list one by one and keep putting the node addresses in a Hash Table. At any point, if NULL is reached then return false, and if the next of the current nodes points to any of the previously stored nodes in  Hash then return true.
#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?
R: Space-time complexity is O(n).








#### How does HashMap work?
R: The Hashtable is a non-generic collection that stores key-value pairs, similar to generic Dictionary collection. It optimizes lookups by computing the hash code of each key and stores it in a different bucket internally and then matches the hash code of the specified key at the time of accessing values
#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)
r: Immutability allows you to get same hash code every time, for a key object.

### Database

#### How can you connect your application to a database server? What are the possible ways?
R: There are a few ways:
You could simply advertise your database connection address and port number on an open connection. This would allow anyone with the right authentication to get into the database using a direct connection, a client browser tool like Toad, or a command-line tool like “mysql” for MySQL or “sqlplus” for Oracle. This wouldn’t be a very “pretty” interface, but would function for both humans and programs. But I certainly don’t advise this as it’s totally insecure and brutally hard to manage.
You could have a simple HTTP interface that accepts a login/password, lets the user enter SQL text, and displays the results. This would be a bit more “controlled” than the above, but not much…
If you want to allow stuff like mobile apps to have access to a database, a pretty standard way to do it is to design an API to the database, and have a server-side app that accepts the inbound API call, keeps connections to the DB, executes the queries appropriate to the API call, and returns results to the caller using a formatted outbound API. Nowadays, these are usually done using JSON as the transport language, although you still have to define what’s actually in the API.

#### What do you know about database normalization?
R: Normalization is the process of organizing data in a database. This includes creating tables and establishing relationships between those tables according to rules designed both to protect the data and to make the database more flexible by eliminating redundancy and inconsistent dependency

### Other

#### What is a garbage collector, in a nutshell?
R: It is a form of automatic memory management. The garbage collector attempts to reclaim memory which was allocated by the program, but is no longer referenced
## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?
R: Type casting is a way of converting data from one data type to another data type. Upcasting is casting to a parent type in simple words casting individual type to one common type is called upcasting while downcasting is casting to a child type or casting common type to individual type.

#### Which order should we catch the exceptions? Why?
R: The order is whatever matches first, gets executed. If the first catch matches the exception, it executes, if it doesn't, the next one is tried and on and on until one is matched or none are.  So, when catching exceptions you want to always catch the most specific first and then the most generic

### Object-oriented

#### What is a class?
R: A class is a user-defined blueprint or prototype from which objects are created. We can say it’s a blueprint. Often we compare it to the matrix that we use to make coockies from drought.

#### What is an object?
R: Object, in C#, is an instance of a class that is created dynamically.

#### What is a constructor?
R: A constructor is a member of a class. It is a method in the class which gets executed when a class object is created

#### Do we require parameter for constructors?
R: No, since when you create a class it already has a default constructor that takes no arguments.



#### What is an interface?
R: Interface is a blueprint of a class. Often it’s reffered as a contract class, and the classes that inherit from it offer implementation for its members.

#### What are access modifiers?
R: Access modifiers are used to specify the scope of accessibility of a member of a class or type of the class itself.

#### What is data hiding?
R: Data hiding means hide some important information of class from other class,method or object. abstraction is a mechanism which allow a class to make visible relevant information and hide unnecessary information

#### Can a static method use non-static members?
R: In static method, the method can only access static data members and static methods of another class or same class but cannot access non-static methods and variables. Also a static method can rewrite the values of any static data member.


#### What is the difference between hiding a static method and overriding an instance method?
R: Method overriding means you are changing the implementation of the method from the base class in the derived class and it requires virtual and override keywork. The other option uses the new keywork and is reference type.

#### Define the following terms: Instantiation, Attribute, Method
R: Instantiation is the creation of a real instance or particular realization of an abstraction or template such as a class of objects or a computer process. To instantiate is to create such an instance by, for example, defining one particular variation of object within a class, giving it a name, and locating it in some physical place.

An attribute is a declarative tag that is used to convey information to runtime about the behaviors of various elements like classes, methods, etc in your program.


Methods are used in C# and are functions that operate through a designated class. A method is a group of statements that together perform a task.




#### Could we access a static variable (or method) from a non-static method? Why?
R: Yes, a non-static method can access a static variable or call a static method. There is no problem with that because of static members  both static variable and static methods belong to a class and can be called from anywhere, depending upon their access modifier.



#### Could we access a non-static variable (or method) from a static method? Why?
R: Yes, static members i.e. both static variable and static methods belong to a class and can be called from anywhere, depending upon their access modifier.

#### How many instances you have of a static variable of a given class?
You can’t have multiple instances.

#### Why is it not a good practice to write a lot of static methods?
R: When you instantiate an object with the same dependencies and arguments, you should be able to rely on it behaving the same way regardless of when and where it was created, right? It would be kind of infuriating otherwise at least.
But when you use a static method, that object is no longer fully in control of it's behavior. Instead of injecting the dependency, where the dependent class has control over its instance, there's no way to know if someone or something else is changing the class in a way that will alter the outcome of your method call.

#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?
R: Static methods can be accessed directly in static and non-static methods.Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.

#### What is the ‘this’ reference?
R: The this is a keyword which is used as a reference to the object of the current class, with in an instance method or a constructor. Using this you can refer the members of a class such as constructors, variables and methods.

#### What are base class, subclass and superclass?
The base class is the parent class.
A class that is derived from another class is called a subclass
The class from which the subclass is derived is called a superclass


#### Difference between overloading and overriding?
R: When two or more methods in the same class have the same name but different parameters, it's called Overloading. When the method signature (name and parameters) are the same in the superclass and the child class, it's called Overriding

#### What are the Object Oriented Principles? Explain the concepts with realistic examples!



#### What is method overloading?
R: Method Overloading is the common way of implementing polymorphism. It is the ability to redefine a function in more than one form. A user can implement function overloading by defining two or more functions in a class sharing the same name. C# can distinguish the methods with different method signatures.

#### What is method overriding?
R: Method Overriding is a technique that allows the invoking of functions from another class (base class) in the derived class. Creating a method in the derived class with the same signature as a method in the base class is called as method overriding.

#### Explain how object oriented languages attempt to simplify memory management for Programmers.
R: They use garbage collector.


#### Explain the “Single Responsibility” principle!
R: The single-responsibility principle (SRP) is a computer-programming principle that states that every module, class or function in a computer program should have responsibility over a single part of that program's functionality, and it should encapsulate that part. All of that module, class or function's services should be narrowly aligned with that responsibility.

#### What is an object oriented program? Explain, show.
Object Oriented programming (OOP) is a programming paradigm that relies on the concept of classes and objects.

#### How do you make a class immutable? What do you need to watch out for?
R:
Step 1: Remove the setters of the class, only have getters.
Step 2: Provide parameters via constructor.
Step 3: Make the variables of the property READONLY

#### How many instances can be created for an abstract class?
R: You can’t instantiate abstract classes
.
## Programming languages

### C&#35;

#### Explain the purpose of IL and how does it relate to CLR?
R: IL code is a CPU independent partially half compiled code. When we write our code in any specific language like (for eg C# language) and compiles the code, respective compiler (i.e. cse.exe compiler) take the action and compiles the c-sharp code into partially half compiled code. This half partially compiled code is known as IL code.

#### What does “managed code” mean?
R: To put it very simply, managed code is just that: code whose execution is managed by a runtime

#### What is an assembly?
R: An assembly is a collection of types and resources that are built to work together and form a logical unit of functionality. Assemblies take the form of executable (.exe) or dynamic link library (. dll) files, and are the building blocks of . NET applications

#### What is the difference between an EXE and a DLL?
R: .exe 1).EXE is Executable File 2).exe is run individually 3).exe Has Main Function 4)Mainly is for standared alone application .DLL 1)DLL is Dynamic Link Library 2)dll can't run individually 3)dll doesn't contain Main Function 4)dll give support to exe

#### What is the difference between `dotnet build` and `dotnet restore`?
dotnet build - Builds a project and all of its dependencies.
dotnet restore - Restores the dependencies and tools of a project.

#### What is strong-typing versus weak-typing? Which is preferred? Why?
Strongly typed means, a variable will not be automatically converted from one type to another. Weakly typed is the opposite. Prefferences depend upon the ussage. Generally strongly typed is safer, but in scripts we can use weak-typing.

#### What is a namespace?
R: In C#, namespaces are used to logically arrange classes, structs, interfaces, enums and delegates.

#### Explain sealed class in C#?
R: When applied to a class, the sealed modifier prevents other classes from inheriting from it.

#### What is explicit vs. implicit conversion? Give examples of both of them.
R: Implicit conversion is the conversion in which a derived class is converted into a base class like int into a float type. Explicit conversion is the conversion that may cause data loss. Explicit conversion converts the base class into the derived class.

#### Is a struct stored on the heap or stack?
R: Structs are allocated on the stack, if a local function variable, or on the heap as part of a class if a class member

#### Can a struct have methods?
R: Yes.

#### Can DateTimes be null?
R: It cannot be null.

#### List out the differences between Array and ArrayList in C#?
R: Array is strongly typed. This means that an array can store only specific type of items\elements. Also in an array we can store only one datatype at a time. ArrayList is the opposite.

#### How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?
R:
IDisposable is an interface that contains a single method, Dispose(), for releasing unmanaged resources, like files, streams, database connections and so on. This method is implemented explicitly in the code when we need to clean up a disposable object and to release unmanaged resources that this disposable object holds.

The using pattern or keyword is a way to allow us to use an expensive object in a deterministic or predictable manner and ensure garbage collection is done after we are done using the resource. For objects that require such deterministic collections we may opt to implement the IDisposable interface to allow for non GC based collection being invoked..


#### How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?
R: By using the using() pattern and also the Dispose() method.

#### Why to use keyword “const” in C#? Give an example.
R: You use the const keyword to declare a constant field or a constant local. Constant fields and locals aren't variables and may not be modified.
Ex: const int X = 0;
We can use it for example for defining PI, which is a constant number always in math.

#### What is the difference between “const” and “readonly” variables in C#?
R: Const fields has to be initialized while declaration only, while readonly fields can be initialized at declaration or in the constructor. const variables can declared in methods ,while readonly fields cannot be declared in methods

#### What is a property in C#?
R: A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field. Properties can be used as if they are public data members, but they are actually special methods called accessors.

#### List out two different types of errors in C#?
R: Run-time error, Syntax error and Logic Error

#### What is the difference between “out” and “ref” parameters in C#?
R: The out keyword is generally used when a method returns multiple values.
The ref is a keyword in C# which is used for the passing the arguments by a reference.

#### Can we override private virtual method in C#?
R:  No, moreover, you cannot access private methods in inherited classes.

#### What's the difference between IEquatable and just overriding Object.Equals()?
R: The main reason is performance. When generics were introduced in .NET 2.0 they were able to add a bunch of neat classes such as List<T>, Dictionary<K,V>, HashSet<T>, etc. These structures make heavy use of GetHashCode and Equals. But for value types this required boxing. IEquatable<T> lets a structure implement a strongly typed Equals method so no boxing is required. Thus much better performance when using value types with generic collections.
Reference types don't benefit as much but the IEquatable<T> implementation does let you avoid a cast from System.Object which can make a difference if it's called frequently.



#### Explain the differences between public, protected, private and internal. Explain access modifier – “protected internal” in C#!
R:
public: The type or member can be accessed by any other code in the same assembly or another assembly that references it.
private: The type or member can be accessed only by code in the same class or struct.
protected: The type or member can be accessed only by code in the same class, or in a class that is derived from that class.
internal: The type or member can be accessed by any code in the same assembly, but not from another assembly.
protected internal: The type or member can be accessed by any code in the assembly in which it's declared, or from within a derived class in another assembly.


#### What’s the difference between using `override` and `new` keywords when defining method in child class?
The override modifier may be used on virtual methods and must be used on abstract methods. This indicates for the compiler to use the last defined implementation of a method. Even if the method is called on a reference to the base class it will use the implementation overriding it.

The new modifier instructs the compiler to use your child class implementation instead of the parent class implementation. Any code that is not referencing your class but the parent class will use the parent class implementation.

#### Explain StringBuilder class in C#!
R: The System.Text.StringBuilder class can be used when you want to modify a string without creating a new object. Using the StringBuilder class can boost performance when concatenating many strings together in a loop.

#### How we can sort the array elements in descending order in C#?
R: First, sort the array using Array.Sort() method which sorts an array ascending order then, reverse it using Array.Reverse() method.

#### Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).
R: Yes, you can.

#### What are Nullable Types in C#?
R: In C#, the compiler does not allow you to assign a null value to a variable. So, C# 2.0 provides a special feature to assign a null value to a variable that is known as the Nullable type.

#### Conceptually, what is the difference between early-binding and late-binding?
R: Early binding refers first compilation of the program . But in late binding object is runtime occurs in program. Also called as Dynamic binding or overriding or Runtime polymorphism

#### What is delegate, event, callback, multicast delegate?
R: A delegate is a type that represents references to methods with a particular parameter list and return type. When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.
An event is a notification sent by an object to signal the occurrence of an action.
A "callback" is a term that refers to a coding design pattern. In this design pattern executable code is passed as an argument to other code and it is expected to call back at some time.
A Multicast Delegate in C# is a delegate that holds the references of more than one function.



#### What is enum in C#?
R: Enumeration (or enum) is a user defined data type in C. It is mainly used to assign names to integral constants, the names make a program easy to read and maintain.

#### What is null-conditional operator?
Available in C# 6 and later, a null-conditional operator applies a member access, ?. , or element access, ?[] , operation to its operand only if that operand evaluates to non-null; otherwise, it returns null .



#### What is null-coalescing operator?
R: The null-coalescing operator ?? returns the value of its left-hand operand if it isn't null; otherwise, it evaluates the right-hand operand and returns its result. The ?? operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.

#### What is serialization?
R: Serialization is the process of converting an object into a stream of bytes to store the object or transmit it to memory, a database, or a file. Its main purpose is to save the state of an object in order to be able to recreate it when needed. The reverse process is called deserialization.

#### What is the difference between Finalize() and Dispose() methods?
R: The finalizer method is called when your object is garbage collected and you have no guarantee when this will happen (you can force it, but it will hurt performance).

The Dispose method on the other hand is meant to be called by the code that created your class so that you can clean up and release any resources you have acquired (unmanaged data, database connections, file handles, etc) the moment the code is done with your object.


#### How do you inherit a class from another class in C#?
R: To inherit from a class, use the : symbol.

#### What is difference between “is” and “as” operators in C#?
R: The difference between is and as operators are as follows: The is operator is used to check if the run-time type of an object is compatible with the given type or not whereas as operator is used to perform conversion between compatible reference types or Nullable types




#### What are indexers in C# .NET?

R: C# indexers are usually known as smart arrays. A C# indexer is a class property that allows you to access a member variable of a class or struct using the features of an array. In C#, indexers are created using this keyword. Indexers in C# are applicable on both classes and structs.


#### What is the difference between returning IQueryable<T> vs. IEnumerable<T>?
R:  Both IEnumerable and IQueryable are forward collection. Querying data from a database, IEnumerable execute a select query on the server side, load data in-memory on a client-side and then filter data. Querying data from a database, IQueryable execute the select query on the server side with all filters.

#### What is LINQ? Explain the idea of extension methods.
R: Linq provides standard query operators like filtering, sorting, grouping, aggregation, and concatenations, and it has many operators to achive many types of functionalities, which are called extension methods, in LINQ.

#### What are the advantages and disadvantages of lazy loading?
R: Advantages:
Improved performance
Less traffic load for the host
Disadvantages:
User experience may be affected. For example, backtracking may not be possible if the page structure is not optimal.
Additional code when integrating with JavaScript
External libraries may be required
JavaScript integration requires that users have scripts enabled
#### How to use of “yield” keyword? Mention at least one practical scenario where it can be used?
The yield keyword signals to the compiler that the method in which it appears is an iterator block. The compiler generates a class to implement the behavior that is expressed in the iterator block. In the iterator block, the yield keyword is used together with the return keyword to provide a value to the enumerator object. This is the value that is returned, for example, in each loop of a foreach statement. The yield keyword is also used with break to signal the end of iteration.

#### By what mechanism does NUnit know what methods to test?
R: By default nunit tests run alphabetically, but you can specify the testing order by adding the attribute “Order” followed by the order number.





#### What is the GAC? What problem does it solve?
The Global Assembly Cache (GAC) is a folder in Windows directory to store the . NET assemblies that are specifically designated to be shared by all applications executed on a system.

#### What is the largest number you can work with in C#?
R: I think it’s ULONG_MAX:
18446744073709551615



