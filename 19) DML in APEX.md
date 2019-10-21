# DML in APEX
## DML Statements in Apex
In Apex, you can use DML (Data Manipulation Language) statements to insert, update, delete, and undelete records in the database. Here are some important things to keep in mind when working with DML statements:

- The number of DML statements is the total number of insert, update, delete, and undelete statements in a single transaction.
- The number of DML rows is the number of records that are inserted, updated, deleted, or undeleted.
### Inserting Records
To insert a record into the database, you can create a new instance of the object and then use the insert statement. Here are some examples:

### Insert a new account record
```apex
Account acc = new Account(Name='TT LLC', Phone ='4250002222');
insert acc;
```

### Insert a new record with a Rating field
```apex
Account acc = new Account(Name='YYY LLC', Phone ='4250003333');
acc.Rating = 'Hot';
insert acc;
```

### Insert a list of accounts
```apex
List<Account> accounts = new List<Account>();
accounts.add(new Account(Name='Test Account 1'));
accounts.add(new Account(Name='Test Account 2'));
accounts.add(new Account(Name='Test Account 3'));
accounts.add(new Account(Name='Test Account 4'));
accounts.add(new Account(Name='Test Account 5'));
insert accounts;
```

### Insert a list of accounts with partial success allowed
```apex
Database.insert(accounts, false);
```

## Updating Records
To update a record in the database, you need to query for the record and then modify its fields. Here are some examples:

### Update a record by ID
```apex
List<Account> accounts = [SELECT Id, Name, Phone FROM Account WHERE Name='SS LLC'AND Phone='4250001234'];
for(Account acc : accounts){
    acc.Name = 'SSLLL LLC';
}
update accounts;
```

### Update a record and its fields by ID
```apex
List<Account> accounts = [SELECT Id, Name, Phone FROM Account WHERE Name='SSLLL LLC'AND Phone='4250001234'];
for(Account acc : accounts){
    acc.Name = 'SSLLL LLC';
    acc.Rating = 'Hot';
}
Database.update(accounts, true);
```
## Deleting Records
To delete a record from the database, you can use the delete statement or the Database.delete method. Here are some examples:

### Delete records by query
```apex
List<Account> accounts = [SELECT Id From Account WHERE Name LIKE 'Test Account%'];
delete accounts;
```

### Delete records using Database.delete method
```apex
Database.delete(accounts);
```
## Undeleting Records
To undelete records in the database, you can query for the deleted records and then use the undelete statement. Here is an example:

### Get deleted account records
```apex
List<Account> deletedAccounts = [SELECT Name, Phone FROM Account WHERE isDeleted=true ALL ROWS];
```
### Undelete records
```apex
undelete deletedAccounts;
```

## Conclusion
When working with DML statements in Apex, it is important to keep in mind the number of DML statements and rows in a single transaction to avoid hitting governor limits. It is also recommended to work with lists of records instead of a single record to improve performance and prevent hitting limits.
