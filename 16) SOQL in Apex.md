# SOWL in Apex
- A list of Account objects is queried, and then a for loop is used to iterate over each object and print its Name and Phone field values.
```apex
List<Account> accounts = [SELECT Name, Phone FROM Account];
```

### Use dot(.) operator to retrieve field values (Ex: account.Name) to get parent records 
```apex
List<Account> accList = [SELECT Name, Phone FROM Account];
for(Account acc : accList){
    System.debug('Account Name: '+ acc.Name + ' Account Phone: '+ acc.Phone);
}
```

### To get a Map<Id, sObject> from an SOQL, write your SOQL in a new Map instance.
- A map of Account objects is queried using the Map<Id, sObject> syntax, and then a for loop is used to iterate over each object and print its Name and Phone field values.
```apex
// new Map<Id, sObject>([ SOQL_QUERY_HERE]);
Map<Id, Account> accMap = new Map<Id, Account>([SELECT Name, Phone FROM Account]);
for(Account acc : accMap.values()){
    System.debug('Account Name: '+ acc.Name + ' Account Phone: '+ acc.Phone);
}
```

### Example in the custom object
- How to query a custom object Book__c and then print the Name and Price__c field values for each record.
```apex
List<Book__c> bookList = [SELECT Name, Price__c FROM Book__c];
for(Book__c book : bookList){
    System.debug('Book Name: '+ book.Name + ' Book Price: '+ book.Price__c);
}
```

### Relation in Apex Example 
- Shows how to query a parent object Account and a child object Case, and then print the Name, Department, and Account.Name field values for each Contact record, along with the CaseNumber field value for each related Case record.
```apex
List<Contact> cons = [SELECT Account.Name, Account.Rating, Name, Department, Title, 
                      (SELECT CaseNumber, Subject 
    					FROM Cases) FROM Contact ORDER BY Name];

for(Contact con : cons){
    System.debug('Contact Name: '+con.Name+', Contact Department: '+con.Department+
                ' Account Name: '+con.Account.Name);
    for(Case caseObj : con.Cases){
        System.debug('Case Number: '+caseObj.CaseNumber);
    }
}
```
