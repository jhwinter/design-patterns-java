# Logger Application Exercise

You are tasked with creating a Logger class that provides a single point of access for logging messages throughout your application. This class should ensure that only one instance of the logger exists to avoid conflicts and ensure consistency in logging behavior.



**Requirements**:

1. Implement the Singleton Pattern to ensure that only one instance of Logger exists.
2. Provide methods to log messages at different levels (e.g., info, warn, error).
3. Each log message should include a timestamp and the log level.
4. Ensure that the logger is thread-safe.



**Task**:

Implement the functionality for the logger using the **Singleton Design Pattern**.



**Instructions**:

1. After implementing the Singleton pattern, test the logger by logging messages at various levels and saving the logs to a file.
2. Ensure that you can only create one instance of the Logger and that all logging calls refer to the same instance.



**Output**:

After executing the code, you should log messages at different levels, save them to a file, and print a confirmation message indicating that the logs were saved successfully.
