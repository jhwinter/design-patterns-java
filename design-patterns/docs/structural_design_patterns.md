# Structural Design Patterns

## Overview

Structural patterns are design patterns that deal with how objects and classes are **composed** to form larger structures, making the system more flexible and easy to understand.

* They simplify the design of complex systems by creating relationships between objects.
* They help in **organizing class hierarchies** and allow for easy modification and extension.



## Adapter Pattern Design

The Adapter Pattern is a structural design pattern that allows objects with incompatible interfaces to work together.

### Problem Statement

Imagine you are working on an **e-commerce application** that needs to send **email notifications** to customers. Currently, you are using your own in-house `EmailNotificationService`, but now you want to integrate a popular third-party email service like **SendGrid**. However, the interface for your in-house system and the SendGrid service are incompatible.

Let's see how the **Adapter Pattern** can solve this problem.

### Adapter Pattern

* **Problem**: When two systems or components have incompatible interfaces, they cannot work together directly.
* **Solution**: The Adapter Pattern bridges the gap by **converting the interface** of one class into another that the client expects.

**Real-world analogy**:
* A **power adapter** that allows a device with a US power plug to fit and work with a European power socket

### Adapter Pattern Examples

* **Adapters in Software Frameworks**: In GUI frameworks, adapters are used to convert legacy code into newer formats.
* **Adapter in Java I/O**: In Java, `InputStreamReader` works as an adapter to convert `InputStream` (byte-based) to `Reader` (character-based).
* **Adapter in APIs**: When integrating external libraries, you often need adapters to convert data formats or APIs to match your system's requirements.

* The Adapter Pattern is a versatile solution to ensure incompatible interfaces work together seamlessly, making it invaluable in software integration and legacy system migration.

### Adapter Pattern Benefits

* **Reusability**: You can reuse existing code even when its interface is not compatible with the current system.
* **Flexibility**: It helps integrate classes from different libraries or systems that were not designed to work together.
* **Decoupling**: The Adapter decouples the client from the specific implementation of the Adaptee.



## Decorator Pattern

You need to add functionality to an object at runtime, but subclassing would lead to an explosion of subclasses or is impractical.

Let’s say we have a simple Pizza ordering system. Initially, we just have plain pizza but now we want to add options such as cheese, olives, tomatoes and mushrooms without modifying the existing pizza class or creating multiple subclasses.

Let's use the **Decorator Pattern** using a Pizza making example where different toppings (like cheese, olives, tomatoes, etc.) can be dynamically added to the base pizza.

**Problem**: In a system where you need to **dynamically extend or add behavior** to objects, inheritance can lead to inflexible and tightly coupled code.

**Solution**: The Decorator Pattern allows you to **add new functionality to objects at runtime** by wrapping them with decorator classes, providing flexibility

**Real-world analogy**:
* A **pizza order** where you start with a basic pizza and add toppings dynamically(e.g., cheese, pepperoni) without modifying the original pizza class.

### Decorator Pattern Benefits

* **Flexible and Scalable**: You can add as many toppings as needed by simply creating a decorator for each topping. No need for subclassing every combination.
* **Single Responsibility Principle**: Each decorator class has one responsibility — to add a specific topping.
* **Open/Closed Principle**: The `BasicPizza` class remains unchanged, and new features(toppings) can be added by creating new decorators.
* **Dynamically Changeable**: Decorators can be added or removed dynamically at runtime.
* **Combinatorial Freedom**: You can mix and match toppings in any order, making the system more flexible and reusable.

### Decorator vs Inheritance

* **Inheritance** is static and applied at compile-time, leading to tight coupling
between base and derived classes.
* **Decorator Pattern** provides a more flexible way to add or remove behavior at
**runtime** without changing the underlying object.



## Proxy Pattern

* **Problem**: Sometimes, direct access to an object might not be desirable due to reasons such as security, resource optimization, or controlled access.
* **Solution**: The Proxy Pattern provides a **surrogate** or placeholder for another object to control access to it.

### Motivation

Imagine a system where we want to load a heavy object like a large image from disk. It might take time to load the image, and we don’t want to load it until it’s necessary. Without using a proxy, the application would load the image every time it's needed, even if not displayed, wasting resources.

### Proxy Design Pattern

* **Virtual Proxy**: Delays the creation of expensive objects until they are needed
(lazy initialization).
* **Protection Proxy**: Controls access based on permissions. 

**Example**
A **large image** loading in an application is expensive, so a virtual proxy is used to load the image only when it’s actually needed (on-demand)

### Proxy Pattern Benefits

1. **Lazy Initialization**: Objects are loaded only when necessary, saving memory and CPU cycles.
2. **Access Control**: You can control access to the real object (e.g., based on user permissions).
3. **Additional Behavior**: Proxies can add additional functionalities like logging, access control, or caching without modifying the real object.
4. **Separation of Concerns**: The real object only deals with its core responsibilities, while the proxy handles ancillary operations like initialization or security.



## Composite Pattern

**Problem**: When building systems like a **file directory**, which consist of both individual items (files) and groups of items (directories), managing these with standard object hierarchies can become complex.

**Solution**: The Composite Pattern allows you to treat **individual objects** and **compositions of objects** uniformly by representing part-whole hierarchies.

* In a **file system**, both **File** and **Directory** can be treated as components. A directory can contain both files and other directories, forming a recursive tree structure.



## Facade Pattern 

### Motivation

In software engineering, a common real-world example of the **Facade Pattern** is an **API Gateway** in a microservices architecture.

**Problem Without Facade**

In a microservices architecture, each microservice can have its own API for specific business logic, such as user management, order processing, and inventory. If the client needs to interact with these microservices, it would need to directly communicate with all the individual services. This would increase the complexity of the client code, tightly couple the client to all the microservices, and expose the inner workings of the system.

**Solution Using Facade (API Gateway)**:

The **API Gateway** acts as a facade, providing a unified interface to the client while handling communication with the underlying microservices. It simplifies client interactions, reduces network calls, and abstracts away the complexity of dealing with multiple services.

### Facade Pattern

**Example: API Gateway as a Facade**

* In **microservices architectures**, an **API Gateway** acts as a facade, providing a simple interface to clients while hiding the complexity of multiple microservices working behind the scenes.

**Problem**: Large, complex subsystems with many classes and methods can be difficult to use directly.

**Solution**: The Facade Pattern provides a simple, unified interface to a complex subsystem, making it easier to interact with.

The **Facade Pattern** is a structural design pattern that provides a simplified interface to a complex system of classes, libraries, or frameworks. Instead of exposing all the details of the complex system, the facade offers a higher-level interface, making it easier to interact with the system. The Facade Pattern is particularly useful when dealing with large systems that contain many interdependent classes, by reducing the interaction points for the client.

### Facade Pattern Benefits

1. **Decoupling**: The client is decoupled from the internal structure of the microservices. Any changes to the underlying services (e.g., changes in APIs or architecture) can be handled within the facade without impacting the client.
2. **Reduced Complexity**: The facade handles the orchestration of complex operations, hiding the complexity of multiple service interactions. This reduces the learning curve for developers working with the system.
3. **Centralized Control**: The facade (API Gateway in this case) can enforce security, logging, caching, and rate-limiting centrally. This avoids duplicating these concerns across multiple services or clients.
4. **Easier Maintenance**: With a facade in place, changes in one subsystem do not ripple out to clients.
For example, if the order service API changes, the facade can adapt without needing to update the client code.
5. **Enhanced Performance**: By consolidating multiple requests into a single call through the facade, you can reduce network overhead, especially in distributed systems like microservices. For example, fetching user details, order details, and payment information in a single request rather than three separate requests. 
6. **Consistency in Interfacing**: The facade ensures a consistent interface for clients, even if the underlying systems evolve over time or become more complex. This helps keep the system modular and more understandable for future changes.



## Bridge Pattern

* **Problem**: You need to separate an object’s **abstraction** from its **implementation** so they can vary independently.
* **Solution**: The Bridge Pattern decouples abstraction from implementation, allowing the two to evolve separately

* A **shape abstraction** that can be implemented using different **rendering
systems** (e.g., Vector or Raster)



## Flyweight Pattern

### Motivation

In game development, especially in scenarios like shooting games where numerous identical bullets are fired, memory and performance can quickly become an issue if each bullet object stores redundant data. Using the **Flyweight Pattern**, we can reduce memory overhead by sharing intrinsic properties of bullets (like appearance) while maintaining unique extrinsic properties (like position and velocity).


### Solution

In this refactor, the `Bullet` class contains only **extrinsic** data like position and velocity. The **intrinsic** data like color is stored in a `BulletType` class, which is shared across all `Bullet` objects. This allows us to manage a large number of bullets efficiently.

### Flyweight Pattern

**Problem**: Creating many identical or similar objects in memory-heavy applications can lead to excessive memory consumption.

**Solution**: By sharing the common state among multiple objects (the **flyweights**), the pattern reduces the memory footprint.

**Example Problem**:
* Consider a graphics system rendering a large number of trees in a forest, where each tree shares the same image but may vary by position or size

The Flyweight Pattern is a structural pattern used to **minimize memory usage** by sharing as much data as possible with similar objects. It separates the ******intrinsic state** (shared) from the **extrinsic state** (non-shared).

**Purpose**: To optimize resource usage in applications that need to handle a large number of similar objects by **reusing** common parts of their data.

**When to Use**:
* When you need to create a large number of objects, and they share a lot of common data.
* Ideal for memory-constrained applications where the object creation cost is high

### Flyweight Pattern Structure

* **Flyweight**: The shared object that stores **intrinsic state** (common data).
* **Concrete Flyweight**: Implements the flyweight interface and shares the intrinsic state.
* **Flyweight Factory**: Manages and creates flyweight objects, ensuring that objects with the same intrinsic state are reused.
* **Client**: Holds and manages the **extrinsic state** (unique information) and delegates behavior to the flyweight.

### Flyweight Pattern Example

**Scenario**: A program that needs to render a large number of trees in a forest.

* **Intrinsic State**: Tree type, shape, texture, and color (shared across trees).
* **Extrinsic State**: Tree position and size (unique per tree).

**Without Flyweight**: Each tree object would store all properties, leading to **high memory usage**.

**With Flyweight**: The tree objects share common properties, and only the unique properties (position and size) are stored separately.
