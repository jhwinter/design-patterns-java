# Report Generator Application Exercise

You are designing a report generation application that allows users to create different types of reports, such as Sales Reports, Employee Reports, and Inventory Reports. Each report has a similar structure but varies in the details and the way data is processed. The application should enable users to generate reports using a template method that defines the skeleton of the report creation process while allowing subclasses to provide specific implementations for certain steps.

**Similarities**:
* All reports follow the same overall structure: gathering data, processing data, formatting the report, and printing it.
* Each report type will use a similar method for outputting the final report.

**Differences**:
* Each report type will have its own specific implementation for gathering and processing data, reflecting the unique characteristics of the report (e.g., sales figures for Sales Reports, attendance records for Employee Reports, and stock levels for Inventory Reports).

**Task**:

Implement the report generation functionality using the **Template Design Pattern**. Your solution should allow for the easy addition of new report types while maintaining the overall structure and flow of the report generation process.

**Output**:

Your program should generate three different reports: a Sales Report, an Employee Report, and an Inventory Report, displaying the structured output for each report type.

**Instructions**:
* You only need to complete the TODOs mentioned in the code.
* Please do not modify any existing code outside of the specified TODO sections.
