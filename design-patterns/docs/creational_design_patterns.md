# Creational Design Patterns

## Overview

**Purpose**: Creational patterns are focused on **object creation mechanisms**, aiming to optimize the creation process while ensuring flexibility.

**Goal**: They abstract the instantiation process to make systems **more flexible and
reusable**.

**Problem They Solve**: Prevent tight coupling between code and object creation logic, simplifying the management of new object creation, especially in complex systems.

**Example**:
* In a system where different types of documents (PDF, Word, Excel) are created, instead of using `new` everywhere, a **Factory Pattern** can centralize object creation.

**Application**: They are applied in scenarios where:
* You want to **separate the instantiation** process from usage.
* The exact type of object needed can vary depending on runtime conditions



## Singleton Design Pattern

### Motivation

In certain situations, such as managing a database connection, logging, or configuration settings, you want to ensure that only one instance of a class is created throughout the application’s lifecycle. If multiple instances were created, it could lead
to issues like:
* **Inconsistent state**: If multiple instances represent the same concept, they may hold different data.
* **Resource conflicts**: If multiple instances of a resource-heavy class are created, it can lead to performance degradation.

### Singleton Design Pattern

The Singleton pattern is used when exactly **one instance** of a class is required to
coordinate actions across the system.

**When to Use**
* **Global resource management** (e.g., managing database connections,
logging).
* **Configuration settings** in applications that need to be shared.

### Singleton Design Structure

* **Private Constructor**: The constructor is private so that no other class can instantiate `AppSettings` directly.
* **Singleton Access**: The `getInstance()` method is used to access the single instance of the settings.
* **Global Access**: Any part of the application can access the settings using `AppSettings.getInstance()`.

### Thread Safety in Singleton DP

**Multi-threading issues**: Without thread safety, multiple instances of the Singleton class could be created in a multi-threaded environment.

**Solutions**:
* **Lazy Initialization with Synchronization**: Synchronize the method that creates the instance.
* **Double-Checked Locking**: Optimize the performance by only locking when necessary.
* **Bill Pugh Singleton Design**: Uses an inner static helper class to ensure thread safety and lazy loading.



## Builder Design Pattern

When an object requires many parameters, especially optional ones, the constructor can become hard to use or maintain. This issue can lead to:

1. Long constructor parameter lists.
2. Difficulty in understanding which values are optional or required.
3. Lack of flexibility when it comes to setting only some values.

For example, constructing an object with multiple optional parameters without the
   Builder pattern can look like this:

**Problem**: When a class constructor has too many parameters, the **Builder Pattern**
allows step-by-step construction of complex objects.

**Solution**: Separates the construction of an object from its representation, offering a
fluent interface for creating complex objects



## Prototype Pattern

### Problem

Consider a board game where you need to save the current state of the game at various checkpoints. Instead of manually creating new board objects and copying all the pieces or their states (which could be costly if the board is large and has many game pieces), we can use the Prototype Pattern to clone the board.

We will use the prototype pattern allows us to make a copy of the current board, including all its pieces and their states, without the need for deeply recreating each part of the board.

### Solution - Prototype Pattern

* The **Prototype Pattern** can be extremely useful in a board game when you want to save the current state of the game (including the board layout and the position of pieces) for undo/redo functionality, checkpoints, or simply making a copy of the board for a new player.
* Each piece or game element can provide its own `clone` method, allowing the entire board to be easily cloned with all its current state.

By using the Prototype pattern, we decouple the complexity of cloning the board from the client, ensuring that each object knows how to clone itself, making the system flexible and easier to maintain.

### Shallow vs Deep Copy

**Shallow Copy**: Creates a new object but **does not clone the objects** that the original object refers to.
**Deep Copy**: Clones the original object and all the objects it refers to (nested objects)

**Example**:
* **Shallow Copy**: Cloning an object with references to other objects (only the outer object is copied).
* **Deep Copy**: Cloning the entire object graph, including any objects the original refers to.

### Benefits

* **Simplifies Object Creation**: Instead of manually copying each object, the `clone` method
in each object simplifies the creation of copies.
* **Avoids Subclassing**: The pattern relies on delegation to the `clone` method, allowing the
class itself to handle object creation, avoiding the need for subclassing.
* **Shallow or Deep Copy**: Depending on the use case, you can either implement a shallow
copy (copying references) or a deep copy (cloning objects) based on the specific
requirements.
* **Efficient Creation**: When creating objects with a complex structure or when performance
is a concern, the Prototype pattern allows you to efficiently replicate objects.
* **Consistency**: Ensures that all properties of the object are consistently copied, avoiding
errors associated with manual copying.

### Use Cases

1. Cloning large objects where construction is costly (e.g., deep configuration settings).
2. When system resources (time, memory) are limited and re-creating objects is expensive.



## Factory Design Pattern

### Motivation

Consider an example of a transportation service app where users can request different types of transport vehicles (e.g., Car, Bike, Bus). You might initially create separate classes for each type, and create instances like this:
```java
Car car = new Car();
Bike bike = new Bike();
```

But as the system evolves, managing object creation directly like this can become complex, especially when adding new types of vehicles.

**Problems**:
1. The client code (i.e., `TransportService`) is tightly coupled to concrete
   classes (`Car`, `Bike`, `Bus`).
2. Adding new transport types requires modifying client code.

### Factory Design Pattern

The **Factory Pattern** helps centralize the creation logic and delegates the responsibility of creating objects to factory classes, which decide the specific class to instantiate. This allows the code to adhere to the **Open/Closed Principle** by letting new types of vehicles be added without modifying the existing code.

1. **Factory Class**: The `TransportFactory` class contains the logic to create different types of transport based on the input string. This abstracts the creation logic and makes it easier to add or change transport types.
2. **Decoupling**: The `TransportService` class (client) no longer needs to
   know the details of how `Car`, `Bike`, or `Bus` are created. It simply calls the factory method.
3. **Flexibility**: Adding a new transport type (e.g., `Truck`) only requires modifying the factory, not the client code

### Factory Design Benefits

1. **Loose Coupling**: The client is decoupled from the specifics of object creation.
2. **Single Responsibility Principle**: The factory class handles the responsibility of object creation.
3. **Open/Closed Principle**: We can easily add new transport types without changing the client code, making the system open to extension and closed to modification.

### Real World Use Cases

1. **GUI Frameworks**: When the type of button or widget to be created is determined at runtime based on the platform (e.g., Windows, macOS, Linux). 
2. **Database Connectivity**: When choosing different types of databases (e.g., SQL, NoSQL) based on configuration. 
3. **Document Conversion Tools**: Where the type of file (e.g., PDF, Word, HTML) to be created depends on user input or settings.

The **Factory Design Pattern** is a fundamental tool to reduce coupling and centralize object creation logic, especially in systems that need to support multiple types of objects.



## Abstract Factory Pattern

### Motivation

Consider an application that needs to support multiple UI themes (e.g., Windows, macOS). Each theme has its own set of UI components such as buttons, scrollbars, and windows. The challenge is to create an architecture that allows switching between these themes without changing the client code that uses the UI
components.

Without the Abstract Factory Pattern, the client code would be tightly coupled with the concrete implementations of buttons, scrollbars, etc., and switching between themes would require modifying the client code.

### Problems in code

1. **Tight coupling**: The client code is tightly coupled to specific implementations of UI components (`WindowsButton`, `WindowsScrollBar`).
2. **Hard to extend**: If we want to add support for macOS UI components, we would need to modify the client code to create instances of `MacOSButton` and `MacOSScrollBar`.

### Abstract Factory Pattern

**Problem It Solves**: Provides an interface for creating **families of related objects** without specifying their concrete classes.

**Structure**:
● **Abstract Factory**: Interface for creating abstract products.
● **Concrete Factory**: Implements the abstract factory and creates concrete products.

Using the Abstract Factory Pattern, you create interfaces for each product (e.g., Button, ScrollBar, Window) and provide a family of concrete implementations for each theme (e.g., WindowsButton, MacOSButton, etc.).

The Abstract Factory provides a way to create a suite of related objects without knowing the exact type of objects that will be created.

### Factory vs Abstract Factory

**Factory Method**: Defines a method in the base class but lets subclasses override it to specify the type of objects that will be created.
* Example: A `DocumentFactory` subclass that creates either PDF or Word documents.

**Abstract Factory**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
* Example: A `GUIFactory` that creates related objects like buttons, checkboxes, and text fields depending on the operating system (Windows or Mac)
