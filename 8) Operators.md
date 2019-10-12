## assignment operator
`Integer x = 5;`
`System.debug('assignment operator - '+x);` // assignment operator - 5

## addition operator
`x = x + 5;`
`System.debug('addition operator - '+x);` // addition operator - 10

## Subtraction operator
`x = x - 5;`
`System.debug('Subtraction operator - '+x);`// Subtraction operator - 5

## multiplication operator
`x = x * 5;`
`System.debug('multiplication operator - '+x);` // multiplication operator - 25

## division operator
`x = x/5;`
`System.debug('division operator - '+x);` // division operator - 5

## increment operator
`x++;` //x = x + 1;
`System.debug('increment operator - '+x);` // increment operator - 6

## decrement operator
`x--;`// x=x-1;
`System.debug('decrement operator - '+x);` // decrement operator - 5

## addition assignment operator
`x += 5;` // x = x+5;
`System.debug('addition assignment operator - '+x);` // addition assignment operator - 10

## subtraction assignment operator
`x -= 5;` // x = x-5;
`System.debug('subtraction assignment operator - '+x);` // subtraction assignment operator - 5

## multiplication assignment operator
`x *= 5;` // x = x*5;
`System.debug('multiplication assignment operator - '+x);` // multiplication assignment operator - 25

## division assignment operator
`x /= 5;` // x = x/5;
`System.debug('division assignment operator - '+x);` // division assignment operator - 5

## using addition operator on strings
`String hello = 'Hello';`
`String world = 'World';`

`System.debug(hello + world);` //HelloWorld
`System.debug(hello + ' ' + world);` //Hello World


`Boolean first = true;`
`Boolean second = false;`
`Boolean result;`

## AND Operator
`result = first && second;` // both first and second is true, then final is true, else it is false

`System.debug('And Operator - '+result);` // And Operator - false

## OR Operator
`result  = first || second;` // both first and second is false, then final is false, else it is true

`System.debug('OR Operator - '+result);` // OR Operator - true


## Equality operator
`result = (first == second);` // if both expressions have the same value, then true, else false
`System.debug('Equality Operator Boolean - '+result);` // Equality Operator Boolean - false

`result = (5 == 5);`
`System.debug('Equality Operator Integer - '+result);` // Equality Operator Integer - true

`result = ('Hello' == 'World');`
`System.debug('Equality Operator String - '+result);` // Equality Operator String - false

## Less than operator
`result = (5 < 6);`
`System.debug('Less than operator - '+result);` // Less than operator - true

## Greater than operator
`result = (5 > 6);`
`System.debug('Greater than operator - '+result);` // Greater than operator - false

## less than or equal to operator
`result = (5 <= 6);`
`System.debug('less than or equal to operator - '+result);` // less than or equal to operator - true

`result = (6 <= 6);`
`System.debug('less than or equal to operator 2 - '+result);` // less than or equal to operator 2 - true

## greater than or equal to operator
`result = (5 >= 6);`
`System.debug('greater than or equal to operator - '+result);` // greater than or equal to operator - false

`result = (6 >= 6);`
`System.debug('greater than or equal to operator 2 - '+result);` // greater than or equal to operator 2 - true

## NOT operator
`System.debug('Not operator before - '+ first);` // Not operator before - true

`first = !first;`
`System.debug('Not operator after - '+ first);` // Not operator after - false

## Ternary operator
`String greeting = '';`
`Integer hour = 10;`

if hour is less than 12, then greeting should be good morning else greeting should be good afternoon

`greeting = (hour < 12) ? 'Good Morning' : 'Good Afternoon';`
`System.debug('Ternary operator 10 - '+ greeting);` // Ternary operator 10 - Good Morning

`hour = 13;`
`greeting = (hour < 12) ? 'Good Morning' : 'Good Afternoon';`
`System.debug('Ternary operator 13 - '+ greeting);` // Ternary operator 13 - Good Afternoon



# Challenge-1
if hour < 12 = Good morning if hour > 12 && hour < 5 = Good Afternoon else Good Evening.

# Challenge-2
1 slice - $8/slice
2-3 slice - $7/slice
more than 3 slice - $6/slice

Ross ordered - 3 slices, Chandler ordered - 1 slice, Joey ordered - 4 slices


## Create rate card with constants
`final Integer ONLY_ONE_SLICE = 8;`
`final Integer UPTO_THREE_SLICES = 7;`
`final Integer MORE_THAN_THREE_SLICES = 6;`

`Integer numberOfSlices = 0;`

## Calculate Ross's amount
`numberOfSlices = 3;`
`Integer rossHasToPay = numberOfSlices == 1 ? ONLY_ONE_SLICE*numberOfSlices :
	(numberOfSlices <= 3 ? UPTO_THREE_SLICES*numberOfSlices :
		MORE_THAN_THREE_SLICES*numberOfSlices);`

`System.debug('Ross has to pay - '+rossHasToPay);` // Ross has to pay - 21

## Calculate Chandler's amount
`numberOfSlices = 1;`
`Integer chandlerHasToPay = numberOfSlices == 1 ? ONLY_ONE_SLICE*numberOfSlices :
	(numberOfSlices <= 3 ? UPTO_THREE_SLICES*numberOfSlices :
		MORE_THAN_THREE_SLICES*numberOfSlices);`

`System.debug('Chandler has to pay - '+chandlerHasToPay);` // Chandler has to pay - 8

## Calculate Joey's amount
`numberOfSlices = 4;`
`Integer joeyHasToPay = numberOfSlices == 1 ? ONLY_ONE_SLICE*numberOfSlices :
	(numberOfSlices <= 3 ? UPTO_THREE_SLICES*numberOfSlices :
		MORE_THAN_THREE_SLICES*numberOfSlices);`

`System.debug('Joey has to pay - '+joeyHasToPay);` // Joey has to pay - 24

 