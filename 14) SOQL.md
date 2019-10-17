# SOQL
## SOQL (Salesforce Object Query Language)
- Is used to query data from Salesforce. It is very similar to SQL (Structured Query Language), with some differences and limitations.

### Basic Sample of SOQL
```sql
SELECT id, Name, Phone FROM Account
```
### Filter Results with Conditions
```sql
SELECT Name, Company, Email, Status FROM Lead WHERE Status = 'Closed-Converted'
```
### OR Keyword
- If one condition is true, then it will retrieve records.
```sql
SELECT Name, Company, Email, Status FROM Lead WHERE Status = 'Closed-Converted' OR Status = 'Closed-Not Converted'
```
### AND Keyword
- Checks whether both conditions are true.
```sql
SELECT Name, Company, Email, Status FROM Lead WHERE Status = 'Closed-Converted' AND Status = 'Closed-Not Converted'
```
### Example Using Three Conditions
```sql
SELECT Name, LeadSource, Company, Email, Status FROM Lead 
WHERE (Status = 'Closed-Converted' AND Status = 'Closed-Not Converted') AND LeadSource = 'Web'
```
### IN Keyword
- Add multiple possible values for a field.
- The IN keyword can give better performance in some circumstances, but it's not guaranteed and can only be confirmed by the query execution plan.

```sql
SELECT Name, LeadSource, Company, Email, Status FROM Lead 
WHERE Status IN('Closed-Converted', 'Closed-Not Converted') AND LeadSource = 'Web'
```
### NOT IN Keyword
- Opposite of the IN keyword.

### LIKE Operator
- Matches partial text string with support of wildcards.

- The LIKE operator is only case-insensitive operator in SOQL.

- Avoid using leading % in LIKE operator, as it leads to full table scan and degrades query performance.

- % wildcard matches zero or more characters.
For example, **LIKE 'fact%'** will match Fact, Facts, Factor, but not isfact or Facial.
```sql
SELECT Name, Department, Title, Phone, Email FROM Contact WHERE Title LIKE '%VP%' AND Department = 'Finance'
```
- `_` wildcard matches exactly one character.
For example, **LIKE '_ine'** will match Mine, Line, Pine, but not Shine or Inevitable.

### ORDER BY Clause
To sort records, for example, a, b, c, d, ... or 1, 2, 3, 4, ...
```sql
SELECT Name, Status, LeadSource FROM Lead ORDER BY Name (or any field name)
```
- By default, SOQL sorts your records in ascending order.

### ASC and DESC Keywords
 - ASC (ascending order)
 - DESC (descending order)
```sql
SELECT Name, Status, LeadSource FROM Lead ORDER BY Name DESC
```
### NULLS FIRST and NULLS LAST
NULLS FIRST: Shows null values at the top.
NULLS LAST: Shows null values at the end.

### LIMIT Clause
- To limit record queries.
```sql
SELECT Name, Status, LeadSource FROM Lead LIMIT 10  -- Will execute first 10 records
SELECT Name, Status, LeadSource FROM Lead ORDER BY CreatedDate DESC LIMIT 2
```
### OFFSET Clause
- Used to point to a particular row.
- The maximum OFFSET that you can set is two thousand.
```sql
SELECT Name, Status, LeadSource FROM Lead OFFSET 5 -- Will skip first 5 records
```
- The OFFSET and LIMIT keywords are generally used for pagination.
```sql
SELECT Name, Status, LeadSource FROM
```