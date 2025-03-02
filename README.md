# Calculation and Graphic Work
Calculation and Graphic Work on the topic "Design Patterns"
This calculation and graphic work explores the following design patterns: Object Pool, Bridge, Null Object, and Reactor.
## Object Pool
Object Pool is a creational design pattern that represents a set of initialized and ready-to-use objects. When the system needs an object, it is not created but taken from the pool. When the object is no longer needed, it is not destroyed but returned to the pool.

### Purpose

The object pool is designed to store ready-to-use objects. When the system requires a new object, it is taken from the pool, avoiding the overhead of creating it. After use, the object is returned to the pool instead of being destroyed.

### Usage Conditions

The pattern is used to improve performance in cases where:

•	Objects are frequently created and destroyed;
•	The system has a limited number of object types stored in the pool;
•	Creating or destroying an object is a resource-intensive operation.

### Features of Usage

The pool knows nothing about the implementation of the objects it stores. Therefore, it is assumed that a returned object is in an undefined state. Before reuse, the object must be reset to its initial state. The presence of objects in an undefined state can turn the pool into an "object cesspool." Reusing objects may lead to data leaks, so it is essential to clear fields containing sensitive data during reset. If the pool runs out of available objects, the system can:

•	Increase the pool size;
•	Deny the request for an object;
•	Queue the request and wait for an object to become available.

### Static Model (Class or Module Diagram) of Object Pool

![Статична модель Object Pool](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/ObjectPoolClassDiagram.jpg)

### Dynamic Model (Interaction or State Diagram) of Object Pool
    
![Динамічна модель Object Pool](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/ObjtctPoolSequenseDiagram.jpg)

## Bridge

Bridge is a structural design pattern that separates abstraction from its implementation, allowing them to vary independently.

### Purpose

The Bridge pattern decouples an abstraction from its implementation so that the two can evolve independently. The terms "abstraction" and "implementation" here do not refer to abstract classes or interfaces in programming languages. Abstraction refers to a high-level control layer that delegates work to the implementation layer.

### Usage Conditions

The Bridge pattern should be used when:

•	There is a need to avoid a permanent binding between abstraction and implementation, especially when the implementation must be selected at runtime;
•	Both abstractions and implementations should be extensible through subclassing;
•	Changes in the implementation should not affect clients, meaning client code should not need recompilation;
•	The implementation should be completely hidden from clients;
•	A single implementation needs to be shared among multiple objects (e.g., using reference counting).

### Static Model (Class or Module Diagram) of Bridge

![Статична модель Bridge](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/BridgeClassDiagram.jpg)

### Dynamic Model (Interaction or State Diagram) of Bridge

![Динамічна модель Bridge](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/BridgeSequenceDiagram.jpg)

## Null object

In object-oriented programming, a Null Object is an object with defined neutral behavior. The Null Object design pattern describes the use of such objects and their behavior (or lack thereof).

### Purpose

Instead of using a null reference to indicate the absence of an object, a special object implementing the required interfaces but having no behavior (empty methods) is used. The advantage of this approach is that the behavior of the null object is always predictable: it does nothing, avoiding the side effects of null references.

For example, a function that reads a list of files in a directory and performs actions on each file can return a null object (e.g., an empty list) instead of null or throwing an exception. This eliminates the need for null checks in the calling code.

### Static Model (Class or Module Diagram) of Null Object

![Статична модель Null Object](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/NullObjectClassDiagram.jpg)

### Dynamic Model (Interaction or State Diagram) of Null Object

![Динамічна модель Null Object](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/ObjtctPoolSequenseDiagram.jpg)

## Reactor

The Reactor pattern is a software design pattern used for event handling that can simultaneously respond to multiple service requests. The key component of the pattern is an event loop running in a single thread or process, which demultiplexes incoming requests and dispatches them to the appropriate request handlers.

### Purpose

The Reactor pattern is a good starting point for solving any concurrent event-handling problem. It is not limited to network sockets; hardware I/O, file system or database access, inter-process communication, and even abstract messaging systems are all potential use cases.

However, the Reactor pattern has limitations, the main one being the use of callbacks, which can complicate program analysis and debugging—a common issue in inversion-of-control designs. Simpler approaches, such as "thread-per-connection" or fully iterative designs, may be acceptable if scalability or high throughput is not required.

Single-threading can become a drawback in cases requiring maximum throughput or when requests require significant processing. Various multithreading constructs can overcome these limitations, and some of them still use the Reactor pattern as a subcomponent for event handling and I/O.

### Static Model (Class or Module Diagram) of Reactor

![Статична модель Reactor](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/ReactorClassDiagram.jpg)

### Dynamic Model (Interaction or State Diagram) of Reactor

![Динамічна модель Reactor](https://github.com/NorthDice/RGR_APPZ_Balychev/blob/main/ReactorSequanceDiagram.jpg)






