# Primitive Data Types
**Primitive Data Types:** String, Integer, Boolean, Long, Decimal, Double, Date, Time, DateTime, Blob, ID

**NOTE:** We cannot assing 'String' to the Integer if we did it gonna give Error

`String student = 'Hello World';`
`System.debug(student);` // Hello World

`Integer numbers = 1234;`
`System.debug(numbers);` // 1234

`Boolean amIDeveloper = true;`
`System.debug(amIDeveloper);` // true

`Long worldPopulation = 70000000000L;`
`System.debug(worldPopulation);` // 70000000000

`Decimal myGPA = 3.8;`
`System.debug(myGPA);` // 3.8

`Double lightSpeed = 93000000/186000;`
`System.debug(lightSpeed);` // 500

`Date tDate = Date.newInstance(2019, 8, 13);`
`System.debug(tDate);` // 2019 - 8 - 13

`Time currentTime = Time.newInstance(2, 19, 0, 0);`
`System.debug(currentTime);` // 02:19:00

## Example:
`Integer greeting = 'Hello World';` 
`System.debug(greeting);` // Illigal Assignment from String to Integere
