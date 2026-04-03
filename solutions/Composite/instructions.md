# Restaurant Menu Application Exercise

In this exercise, you will implement the Composite Design Pattern to model a Restaurant Menu System. The goal is to create a hierarchical structure where both individual menu items and composite menu sections (like categories or submenus) can be treated uniformly. This will allow you to display the menu and manage menu items effectively.



**Requirements**:

1. Create a MenuComponent abstract class with the following methods:
   * print(): Prints the details of the menu item or menu section.

2. Implement a MenuItem class that:
   * Extends the MenuComponent class.
   * Contains attributes for the name, description, and price of the item.
   * Represents a single menu item that can be printed.

3. Implement a MenuSection class that:
   * Extends the MenuComponent class.
   * Contains a list of MenuComponent objects (which can be either individual menu items or other menu sections).
   * Represents a composite menu section that can contain multiple menu items and sub-sections.
   * Supports method to add menu components.

4. Implement a client class that:
   * Demonstrates the use of the composite pattern by creating various menu items and grouping them into menu sections.
   * Displays the complete menu structure.


**Output**:

After executing the code, it will simulate the following sequence of operations:

* Create menu sections to categorize these items (e.g., appetizers, main courses, desserts).
* Create individual menu items with names, descriptions, and prices.
* Construct a complete menu that includes various sections and items.
* Print the entire menu structure, clearly displaying all menu items and their respective sections.

Each operation should be clearly reflected in the output, confirming that the composite pattern effectively manages both individual menu items and composite menu sections uniformly.
