# Exception Handling in Apex

Apex uses exceptions to note errors and other events that disrupt the normal flow of code execution.

## Try-Catch-Finally Blocks

The try, catch, and finally statements can be used to gracefully recover from a thrown exception.

- Catch block only executes if the exception was thrown in try block and matches its exception type.
- Finally block always executes regardless of whether an exception was thrown.
- A try block must be followed by a catch block or by finally block.
- You can define multiple catch blocks but there can be only finally block per try block.

### Example 1: Only Math Exception
```apex
try {
    // Math Exception
Double result = 10/0;
System.debug('Result ' + result);
} catch (MathException e) {
System.debug('Caught Math Exception');
} finally {
System.debug('Finally block');
}
```

### Example 2: Math and DML Exceptions
```apex
try {
// DML Exception
Account acc = new Account();
insert acc;
} catch (MathException e) {
System.debug('Caught Math Exception');
} catch (DMLException e) {
System.debug('Caught DML Exception');
} finally {
System.debug('Finally block');
}
```

### Example 3: Handling Multiple Exceptions
```apex
try {
// Math Exception
Double result = 10/0;
System.debug('Result ' + result);

// DML Exception
Account acc = new Account();  
insert acc; 

// Null Pointer Exception
String str;
System.debug(str.toLowerCase); 

// Throw an Exception programmatically
throw new NullPointerExeption();

} catch (Exception e) {
System.debug('Caught Generic Exception');
} finally {
System.debug('Finally block');
}
```


### Example 4: Common Exception Methods
```apex
try {
// Math Exception
Double result = 10/0;
System.debug('Result ' + result);

// DML Exception
Account acc = new Account();  
insert acc;  

} catch (Exception e) {
System.debug('Cause: ' + e.getCause()); // Cause null
System.debug('Message: ' + e.getMessage()); // Divide by 

System.debug('Line Number: ' + e.getLineNumber()); // Line Number 4

System.debug('Stack Trace: ' + e.getStackTraceString()); // Stack Trace 
AnonymousBlock: line 4, column 1

} finally {
System.debug('Finally block');
}
```

## Creating Custom Exception

- All exceptions (built-in & custom), must extend the Exception class.

---

By handling exceptions effectively, you can ensure that your Apex code is more resilient and your applications have a better user experience.
