# Relationship Queries
## Parent to Child Query
- To query child records from a parent object, the main object for the query should be the parent object. Only one level deep child records from a parent object to child is supported, and up to 20 related objects are supported. Here are some examples:
```sql
SELECT Id, Name, (SELECT Name, RollNumber FROM Students) FROM School

SELECT Name, Phone, Website, (SELECT Name, Email, Department FROM Contacts) FROM Account

SELECT Name, Phone, Website, (SELECT Name, Email, Department FROM Contacts WHERE Department = 'Finance') 
FROM Account // with WHERE keyword 

SELECT Name, Phone, Website, (SELECT Name, Email, Department FROM Contacts WHERE Department = 'Finance'),
(SELECT Name FROM Opportunities) FROM Account //with two child object 

// Custom object relationship name must have a suffix__r.
SELECT Name, (SELECT Name FROM Books__r) FROM Author__c
```

## Child to Parent Query
- To query parent records from a child object, the main object for the query should be the child object. Only 5 levels of child-to-parent are supported, and up to 55 related objects are supported. Here are some examples:
```sql
SELECT Name, RollNumber, School.Name, School.RegistrationNumber FROM Student 

// Reaching for child object 
SELECT Name, Phone, Account.Name, Account.Website FROM Contact

// Reaching for grandparent object 
SELECT Name, Phone, Account.Name, Account.Website, Account.Owner.Name FROM Contact

// Reaching on custom objects
SELECT Name, Author__r.Name FROM Book__c

SELECT Account.Name, Account.Rating, Name, Department, Title, (SELECT CaseNumber, Subject 
FROM Cases WHERE IsClosed = false) FROM Contact WHERE Department = 'Technology' 
AND Account.Rating = 'Hot' ORDER BY Name
```
**NOTE:** When querying for child-to-parent records, you can also use subqueries to access other related objects.