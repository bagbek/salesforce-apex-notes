# For more information please check the documantation. 

# What is Apex?
 Apex is a strongly typed, object-oriented programming language that is designed to work with the Salesforce platform. Using syntax that looks like Java and acts like database stored procedures. 

# Hello World in the Apex
//to see the output, you to open Logs and check the Debug Only
`System.debug('Hello World');` // Hello World
`System.debug('My second Apex Code');` // My second Apex Code

# Variables & Heap
In programming, variables serve as containers that store data in the program's heap, which is a designated portion of RAM allocated to the program. It's worth noting that excessive heap usage can lead to an unresponsive operating system or program, as it may result in memory allocation problems. Therefore, it's crucial to exercise caution when working with variables, as each one takes up memory.
In Apex, there is a strict limit of 6 MB for the heap size of each program, which is a considerable amount in computer terms. As a best practice, developers should try to minimize heap usage whenever possible. However, if too many variables are declared and not used or not cleared properly, the Apex program may encounter a heap size error. To prevent this, it's important to regularly clear or nullify variables to free up memory.

## Example:
`String greeting = 'Hello World';`
`System.debug(greeting);` // Hello World