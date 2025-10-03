# Object Oriented Programming Recap

## Key Concepts in OOP

1. Encapsulation
2. Abstraction
3. Inheritance
4. Polymorphism

### Encapsulation

* Binding data (variables) and methods (functions) together into a single unit, usually a class.
* Control **access to data** via access modifiers (e.g., private, public).
* Example: **Getters and setters** in a class to access and update private data members.

### Abstraction

* Hiding unnecessary details and showing only the essential information.
* Focus on **what an object does**, not **how it does it**.
* Example: Defining a method `draw()` in a `Shape` class without revealing the
drawing logic (implemented by subclasses like `Circle`, `Rectangle`).

### Inheritance

* Mechanism for creating new classes based on existing classes.
* Helps in code **reuse** and establishing relationships between objects.
* Example: `Car` class inherits from `Vehicle` class and adds specific behavior like `startEngine()`.

### Polymorphism

* Allows one interface to be used for a general class of actions.
* Achieved through **method overriding** (runtime polymorphism) or **method
  overloading** (compile-time polymorphism).
* Example: A single method `area()` can be used for different objects like
  `Circle`, `Rectangle`, with different implementations.



### Small Note on Access Modifiers

1. Default / package-private - visible within same package
2. public - visible everywhere
3. private - only visible within the class
4. protected - only visible within the class and child classes
