
# Document Editor Application Exercise

You are tasked with developing a Document Editor that allows users to create and edit text documents. Each character in the document has specific formatting attributes (like font style, size, and color), which can lead to a large memory footprint if each character object is created independently. To optimize memory usage and enhance performance, utilize the Flyweight Design Pattern to share common character attributes among multiple character instances.



**Task**:

Implement the **Flyweight Design Pattern** to create a system that allows users to:

* Create a Character Class:
  * Implement a Character class that represents individual characters in the document. Each character should have attributes like character, font style, font size, and color.
* Character Factory:
  * Implement a CharacterFactory class that manages the creation and sharing of character objects. This factory should return existing character instances if they already exist to avoid duplicating objects with the same attributes.
* Document Class:
  * Create a Document class that represents the text document. This class should maintain a list of characters and utilize the CharacterFactory to get the character instances based on user input.
* Rendering Method:
  * Implement a method in the Document class to render the document, displaying each character's details.
* Test Case:
  * Create a simple test case to demonstrate the functionality of the Document Editor, including adding characters with different attributes and rendering the final document.



**Output**:

After executing the code, it will simulate the following sequence of character manipulations:

* Create characters with specified attributes (like font style, size, and color) based on input received from the backend.
* Render the document, displaying each character along with their shared attributes.
* Confirm that characters with the same attributes are shared efficiently, demonstrating that the memory footprint is optimized.
