# Handling Exceptions in Apex
Apex uses exceptions to note errors and other events that disrupt the normal flow of code execution. In this context, an exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions. You can use exception handling to write code that can recover from these events, instead of allowing them to halt the program.

## Throwing an Exception
You can use the throw keyword to generate an exception programmatically. Here is an example of how to throw a **NullPointerException**
```apex
throw new NullPointerException();
```
## Catching Exceptions
When an exception is thrown, you can use a try-catch block to handle the exception. Here is an example of how to catch a **NullPointerException**
```apex
try {
    String str;
    System.debug(str.toLowerCase());
} catch (NullPointerException e) {
    System.debug('Caught Exception: ' + e.getMessage());
}
```
**NOTE:** In the above example, if str is null, a NullPointerException is thrown, which is caught by the catch block. The catch block logs a message to the debug log, including the message associated with the exception.

## Exception Types
There are many types of exceptions in Apex, including:

- **ArithmeticException:** thrown when an arithmetic operation produces an exception, such as division by zero
- **DmlException:** thrown when a DML operation fails, such as inserting a record with a required field that is not set
- **NullPointerException:** thrown when an attempt is made to use a null reference
- **TypeException:** thrown when an attempt is made to assign an incompatible data type to a variable

## Best Practices
It is a best practice to catch exceptions that you expect to occur, and allow exceptions that you do not expect to propagate up the call stack. This helps you write code that is more resilient and less likely to fail unexpectedly. Additionally, you should log exceptions to the debug log, so that you can investigate and resolve them later.

## Example: Handling Exceptions
```apex
try {
    Double result = 10/0; // This will throw a math exception
} catch (MathException e) {
    System.debug('An error occurred: ' + e.getMessage()); // Handle the exception
}

try {
    Account acc = new Account(); // This will throw a DML exception
    insert acc;
} catch (DmlException e) {
    System.debug('An error occurred: ' + e.getMessage()); // Handle the exception
}

try {
    String str;
    System.debug(str.toLowerCase); // This will throw a null pointer exception
} catch (NullPointerException e) {
    System.debug('An error occurred: ' + e.getMessage()); // Handle the exception
}

try {
    throw new NullPointerException(); // Throw an exception programmatically
} catch (NullPointerException e) {
    System.debug('An error occurred: ' + e.getMessage()); // Handle the exception
}
```