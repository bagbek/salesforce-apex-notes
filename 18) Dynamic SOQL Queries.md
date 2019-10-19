# Dynamic SOQL Queries
## Building SOQL Queries Dynamically in Apex
- You can build your SOQL queries at runtime in apex code dynamically. Dynamic SOQL enables you to create more flexible applications.
```apex
String dynQuery = 'SELECT Id, Name FROM Account';
if(accountType == 'Red'){
    dynQuery += 'WHERE Rating = \'Hot\' AND Amount > 100,000';
}
List<Account> accounts = Database.query(dynQuery);
```
### Here's an example:
```apex
String accountClass = 'Class1';
String queryString = 'SELECT Id, Name, Phone, Rating FROM Account';
if(accountClass == 'Class1'){
    queryString += ' WHERE Rating =\'Hot\' AND Type =\'Prospect \'';
}else if(accountClass == 'Class2'){
   queryString += ' WHERE Rating =\'Warm\' AND Type =\'Other\'';
}else{
    queryString += ' WHERE Amount > 100000';
}
List<Account> accounts = Database.query(queryString);
System.debug('Accounts '+accounts);
System.debug('Accounts size: '+accounts.size());
```
- In the above example, we are building a dynamic SOQL query based on the accountClass variable. Depending on the value of accountClass, we add additional WHERE clauses to our query. Finally, we execute the dynamic query using Database.query() and retrieve a list of Accounts.