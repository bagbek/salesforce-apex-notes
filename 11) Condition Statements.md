# 1. **if-else** 
`Boolean isItSunny = false;`

`Boolean isItRaining = false;`

`Boolean areYouWorking = false;`

## Basic example
`if(isItSunny == false){ `  

// you make the if( !isItSunny) means false

    `System.debug('Do not go to the Party');`

`}else if(isItRaining == true){ ` 

// and here if(isItRaining) means true

    `System.debug('Do not go to the Party');`
`}else if(areYouWorking == true){`

    `System.debug('Do not go to the Party');`

`}else{`

    `System.debug('Yaay it is party time');`
`}`


# 2.  **Switch - When**
Check one expression for multiple values and control the code flow.
`Integer currHour = 11;`

`switch on currHour {

    when 1,2,3,4,5,6,7,8,9,10,11 {
        System.debug('Good Morning');
    }
    when 12,13,14,15,16 {
        System.debug('Good Afternoon');
    }
    when else {
        System.debug('Good Evening');
    }
}`


## Challenege leap year
A year is a leap year, if it is evenly divisible by 4. Except if that is also evenly divisible by 100. Unless the year is also evenly divisible by 400.

`Integer year = 2000;`

`if(Math.mod(year, 4) == 0){

    if(Math.mod(year, 100) == 0){
        if(Math.mod(year, 400) == 0){
            System.debug('It is a leap year');
        }else{
            System.debug('Not a leap year');
        }
    }else{
        System.debug('It\'s a leap year');
    }
}else{
    System.debug('Not a leap year');
}`


