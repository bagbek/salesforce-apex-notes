# 1. Do-While Loop

It always executes at least once because the condition is checked at the end.

```java
Integer year = 1100;
do {
    System.debug('Processing year: ' +year); 
    if(Math.mod(year, 4) == 0){
        if(Math.mod(year, 100) == 0){
            if(Math.mod(year, 400) == 0){
                System.debug(year +' Leap year');
            }
        }else{
            System.debug(year +' is a leap year');
        }
    } year ++;
} while(year <= 2000);

System.debug('Year value after loop: ' +year); // Execute: 2001

// Challenge for do while 
Integer num = 1;
do{
    if(Math.mod(num, 3) == 0 && Math.mod(num, 5) == 0){
        System.debug(num +' fizzBuzz');
    }else if(Math.mod(num, 3) == 0){
        System.debug(num +' fizz');
    }else if(Math.mod(num, 5) == 0){
        System.debug(num + ' Buzz');
    }else{
        System.debug(num);
    }
    num++;
} while(num <= 100);
```


# 2. While Loop
It only executes if the condition is met.
```java
Integer year = 100; 
while(year <= 200){
    // Check if year is a leap year
    year++; // Variable increment statement
}

// Example:
Integer num = 1;
while(num <= 100){
    if(Math.mod(num, 3) == 0 && Math.mod(num, 5) == 0){
        System.debug(num +' fizzBuzz');
    }else if(Math.mod(num, 3) == 0){
        System.debug(num +' fizz');
    }else if(Math.mod(num, 5) == 0){
        System.debug(num + ' Buzz');
    }else{
        System.debug(num);
    }
    num++;
}

// Challenge: Fibonacci
Integer x = 0;
Integer y = 1;
Integer z = 0;

system.debug(x);
system.debug(y);

while(z <= 20){
    z = x + y;
    system.debug(z);
    x = y;
    y = z;  
}
```

# 3. For Loop
```java
for(Integer i = 0; i < 20; i++){
    // Check if i is a leap year
}

// Example:
for(Integer num = 100;  num < 200; num++){
    if(Math.mod(num, 3) == 0 && Math.mod(num, 5) == 0){
        System.debug(num +' fizzBuzz');
    }else if(Math.mod(num, 3) == 0){
        System.debug(num +' fizz');
    }else if(Math.mod(num, 5) == 0){
        System.debug(num + ' Buzz');
    }else{
        System.debug(num);
    }
}

// Challenge: 
for(Integer i = 0; i < 5; i++){
    String x = '';
    for(Integer j = 0; j <= i; j++){
        x += '$';     
    }
    System.debug(x);
}
```


# Break and Continue Statements
The break statement is used to come out of the loop instantly. The continue statement skips the current iteration of a loop.
```java
// Break statement
Integer n = 10;
for(Integer i = 0; i < n; i++){
    if(i == 8){
        break;
    }else{
        System.debug(i);
    }
}
```

