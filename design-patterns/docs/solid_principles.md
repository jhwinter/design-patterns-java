# SOLID Principles

The SOLID principles are a set of five design principles in object-oriented programming and software design. 
They aim to make software more understandable, flexible, and maintainable by following a structured approach.

S – Single Responsibility Principle (SRP)

O – Open/Closed Principle (OCP)

L – Liskov Substitution Principle (LSP)

I – Interface Segregation Principle (ISP)

D – Dependency Inversion Principle (DIP)

## S – [Single Responsibility Principle (SRP)](../src/main/java/org/prateek/SOLIDPrinciples/SRP)

A class should have only one reason to change, meaning it should only have **one responsibility**.

Example: A `User` class should only handle user-related logic, while database-related
operations should be handled by a separate `UserRepository` class.

## O – [Open/Closed Principle (OCP)](../src/main/java/org/prateek/SOLIDPrinciples/OCP)

Software entities (classes, modules, functions) should be **open for extension** but **closed for modification**.

Example: Adding new functionality to a system using **inheritance** or
**composition** without modifying existing code.

## L – [Liskov Substitution Principle (LSP)](../src/main/java/org/prateek/SOLIDPrinciples/LSP)

The **Liskov Substitution Principle (LSP)** states that objects of a superclass should be replaceable with objects of a subclass without altering the correctness of the program. It ensures that a subclass can stand in for its parent class and function correctly in any context that expects the parent class.

No client should be forced to depend on methods it doesn't use. Split large interfaces into smaller, more specific ones.

## I – [Interface Segregation Principle (ISP)](../src/main/java/org/prateek/SOLIDPrinciples/ISP)

The **Interface Segregation Principle** ensures that classes are not burdened with methods they don’t need. It promotes better design by breaking large, general-purpose interfaces into smaller, more specific ones.

It improves **maintainability**, **flexibility**, and **testability** by ensuring that classes
only have the dependencies they actually require.

## D – [Dependency Inversion Principle (DIP)](../src/main/java/org/prateek/SOLIDPrinciples/DIP)

High-level modules should not depend on low-level modules; both should
depend on **abstractions**.
