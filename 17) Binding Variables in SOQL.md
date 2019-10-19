# Binding Variables in SOQL
## Using Apex Variables in SOQL Queries
- You can use Apex variables in SOQL using a colon(:). These variables are called bind variables.
```apex
Set<Id> accountIds = new Set<Id>();
[SELECT Id, Name, Rating FROM Account WHERE id IN :accountIds];

String leadName = 'ABC LLC';
[SELECT Id, Name FROM Lead WHERE Name = :leadName];
```
### Bind expressions can be used as:
- The filter literals in WHERE clause
- The value of the IN or NOT IN operator in WHERE clause, allowing filtering on a dynamic set of values. Note that this is of particular use with a list of IDs or Strings, though it works with lists of any type.
- The numeric value in LIMIT clauses.
- The numeric value in OFFSET clauses.

### Example with a colon(:) binding:
```apex
List<String> accountName = new List<String>();
accountName.add('Test Account');
accountName.add('test');
accountName.add('ABC');
accountName.add('United Oil & Gas Corp.');
List<Account> accounts = [SELECT Id, Name, Rating FROM Account WHERE Name IN :accountName];
System.debug('Account Size: ' + accounts.size());
System.debug('Account: ' + accounts);
```