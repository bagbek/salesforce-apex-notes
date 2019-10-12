## Storing student marks as string values
`String physicsMarks = '72';`
`String chemistryMarks = '64';`
`String mathMarks = '87';`

## Starting with integer 
`Integer total = Integer.valueOf(physicsMarks) + Integer.valueOf(chemistryMarks) + Integer.valueOf(mathMarks));`

`System.debug('Total - '+total);` // Total - 223 

## What if we need to start with String 
`String total = String.valueOf(
                    Integer.valueOf(physicsMarks) + Integer.valueOf(chemistryMarks) + Integer.valueOf(mathMarks));`

`System.debug('Total - '+total);` // Total - 223