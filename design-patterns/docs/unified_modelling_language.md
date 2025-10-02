# Unified Modelling Language (UML)

## Class Diagrams

**Class Diagram**: Represents the static structure of a system, showing classes, attributes, methods, and the relationships between them (inheritance, association, etc.).

```java
class Player {
    private String name;
    public void pay() {}
}
```

```mermaid
classDiagram
    class Player
    Player : -name
    Player : +pay()
```

> By default, we can assume that all attributes are private and all methods are public.

## Association

**Association** represents a relationship between two or more classes. In this case, each object in one class is associated with one or more objects of another class.

[AssociationExample](../src/main/java/org/prateek/Basics/UML/AssociationExample.java)

```mermaid
classDiagram
    Teacher <-- Student : association
```

## Aggregation

**Aggregation** is a weak "has-a" relationship where one class contains objects of another class. However, the contained objects can exist independently of the container object. 

[AggregationExample](../src/main/java/org/prateek/Basics/UML/AggregationExample.java)

```mermaid
classDiagram
    Department --o Professor : aggregation
```

## Composition

**Composition** is a strong "has-a" relationship, where one class owns objects of another class. If the container object is destroyed, the contained objects are destroyed as well. 

[CompositionExample](../src/main/java/org/prateek/Basics/UML/CompositionExample.java)

```mermaid
classDiagram
    House *-- Room : composition
```

### Composition vs Aggregation

```mermaid
classDiagram
    Company *-- Team : composition
    Team o-- Employee : aggregation

    note "Company has Teams. Teams have Employees."
    note for Company "Company owns Teams"
    note for Team "Team cannot exist outside of Company"
    note for Employee "weak association between Team and Employee because Employee still exists outside of Team"
```

## Inheritance

**Inheritance** defines an "is-a" relationship where a subclass inherits properties and behaviors (methods) from a superclass.

[InheritanceExample](../src/main/java/org/prateek/Basics/UML/InheritanceExample.java)

```mermaid
classDiagram
    Animal <|-- Dog : inherits from
```

## Dependency

This is a relationship where one class relies on another in some way, often through method parameters, return types, or temporary associations.

[DependencyExample](../src/main/java/org/prateek/Basics/UML/DependencyExample.java)

```mermaid
classDiagram
    Printer ..> Document : depends on
```

## Realization

A class implements the behavior defined by an interface.

[RealizationExample](../src/main/java/org/prateek/Basics/UML/RealizationExample.java)

```mermaid
classDiagram
    Payment <|-- CreditCardPayment : implements
```

## Summary

* **Association**: Objects are related but can exist independently.
* **Aggregation**: A weak "has-a" relationship where the contained objects can exist independently.
* **Composition**: A strong "has-a" relationship where the contained objects cannot exist without the container.
* **Inheritance**: A subclass inherits from a superclass (is-a relationship).
* **Dependency**: One class depends on another for its functionality.
* **Realization**: A class implements the behavior defined by an interface.
