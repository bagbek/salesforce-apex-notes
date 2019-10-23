# SObject Datatype
## Introduction
In Apex, any standard or custom object is an SObject, and it can be called as the parent of all objects. This means that any record in Salesforce can be represented by an SObject.

## Retrieving Data Using SObject
The get method returns an Object value, which must be typecasted to a primitive datatype. Here's an example that retrieves data from the Account object:
```apex
List<SObject> accounts = [SELECT Name, Phone FROM Account];
for(SObject acc : accounts){
    System.debug('Account Name: '+ String.valueOf(acc.get('Name'))+', Account Phone: '
                + (String)acc.get('Phone'));
}
```
## Retrieving Parent Object Using SObject
To retrieve parent objects, use the getSObject method. Here's an example that retrieves data from the Contact object and its related parent Account object:
```apex
List<SObject> contacts = [SELECT Name, Phone, Account.Name FROM Contact];
for(SObject con : contacts){
    System.debug('Contact Name: '+ String.valueOf(con.get('Name'))+', Contact Phone: '+
                 (String)con.get('Phone') +', Account Name: ' + 
                 (String)con.getSObject('Account').get('Name'));
}
```
## Creating New SObject Record
To create a new SObject record, use the newInstance method from the Type class. Here's an example that creates a new Account record:
```apex
SObject accountRec = (SObject)Type.forName('Account').newInstance();
accountRec.put('Name', 'Sample SObject Account');
accountRec.put('Phone', '2453334444');
insert accountRec;
```
**NOTE:** Always remember to use typecasting while using the get method to retrieve data from an SObject. This ensures that the retrieved data is of the correct data type.