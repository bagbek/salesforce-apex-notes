[For more Click Here](https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_methods_system_string.htm)

# String 

`String str = ' i am a string variable ';`
`System.debug('Actual String: '+str);` //i am a string variable

## Capitalize String
`System.debug('Capitalize String: '+str.capitalize());` // Capitalize String: I am a string variable

## Contains Example
`System.debug('Contains ring? :'+ str.contains('ring'));` // true

## Convert to Upper Case
`System.debug('Upper case: '+str.toUpperCase());` // I AM A STRING VARIABLE

## Convert to Lower Case
`System.debug('Lower case: '+str.toLowerCase());` // i am a string variable 

## equals
`System.debug('Is equal to ring?: '+str.equals('ring'));` // Is equal to ring?: false

`String str1 = 'Jack';`
`String str2 = 'jack';`
`System.debug('str1 equals str2: '+str1.equals(str2));` // str1 equals str2: false

`System.debug('str1 equals str2 ignore case: '+str1.toLowerCase().equals(str2.toLowerCase()));` // str1 equals str2 ignore case: true

## remove
`System.debug('Remove ring: '+str.remove('ring'));` // Remove ring: I am a st variable 

## replace
`System.debug('Replace ring: '+str.replace('ring', 'rong'));` // Replace ring:  I am a strong variable 

## split
`System.debug('Split by space: '+str.split(' '));` // Split by space: (, I, am, a, string, variable)