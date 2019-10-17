# OOPS(Object Oriented Programming System)

# Object - Real life Entity
## Class 
A blueprint for creating objects. It defines the variables (also known as properties) and methods (also known as behaviors) that an object will have.
- Variables/Properties: Attributes of an object such as Name, Age, Roll Number, Class.
- Methods/Behaviors: Actions that an object can perform such as markAttendance(), payFee(), getDues().

## Four Pillars of Object-Oriented Programming
1. Encapsulation
2. Abstraction
3. Inheritance
4. Polymorphism

### Encapsulation: 
- The process of hiding the implementation details of an object from the outside world and restricting access to its internal state. This is achieved by making the variables and methods private, and exposing them through public methods.
### Abstraction: 
- The process of hiding the complexity of an object and exposing only the necessary details to the user. This is achieved by defining interfaces that specify the methods that an object can perform, without revealing how they are implemented.
### Inheritance 
- A mechanism that allows a class to inherit the properties and methods of another class. If a class inherits an interface, it must provide definitions for all the methods declared in the interface, otherwise a compile time error will occur.
### Polymorphism 
The ability of an object to take on many forms. It allows multiple definitions of a method with the same name but different parameters or implementation.

## Apex Class 
- In Salesforce, you cannot create a class without assigning it an access modifier, which can be either Public or Global. You cannot create a private class.
- Each method in Apex must have a return type specified before its name.
### Access Modifiers 
1. **Private:** Default access modifier. Can be used with variables, methods, and inner classes. Restricts access within the outer class scope.
2. **Protected:** Can be used with variables and methods. Inner classes and classes that extend the outer class can access these variables and methods.
3. **Public :** Can be used with classes, variables, and methods. Unrestricted access within the same namespace.
4. **Global:** Unrestricted access.

### Method 
1. **Access Modifier:** Optional but by default private.
2. **Special Keyword:** Optional. Can be static or override.
3. **Return Type:** Required. Can be any data type.
4. **Method Name:** Required. Can be any value.
5. **Parameters** Optional. Can have any data type and any number of parameters.
6. **Method body** { } Required.

```apex
public static Integer add(Integer number1, Integer number2){
      Integer sum = number1 + number2;
      return sum;
}
```
- Return: Must for all return types except void.
- You can access private variables in class methods.
- A method can have multiple return statements, but at least one of the statements must be the last statement of the method.
- Static: When you make a variable STATIC, it will not belong to any method and it will belong to the class itself. You cannot use static variables with class instance/object as these variables are attached to the class itself.
  
### Naming Convention
- Apex is a case-insensitive language.
- Apex Class Name should be Pascal case, which means starting with a capital letter (ExampleClassName).
- Variable and Method Name should be camel case, which means starting with small cases (exampleVariableName).
- Constant Variables should be in all capitalized (FINAL_VARIABLE_NAME).
- Apex does not allow duplicate class name and variable name.
### Class Constructor
- The name of a constructor is always the same as the class name, and they are called automatically when you initialize a class. Constructors cannot return anything as they are auto-called.
- Constructors can be used to get input from the user.
- **this.** keyword refers to the current instance of the class.
- **this()** will call the constructor without parameters, and you must call it first.
  
## Initialization Block
```apex
{
    // code block
}
```
- In the Initialization block, you cannot accept any value from the user.
- Initialization blocks are attached to each instance of the class, so they do not share values.
- But static Initialization blocks are attached to the class and shared across the entire org.
- When you call:
    - Static Initialization block will execute.
    - Initialization block will execute