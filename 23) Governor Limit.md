# Governor Limit Overview
## Salesforce: A Multitenant Cloud
Salesforce is a cloud-based software as a service (SaaS) customer relationship management (CRM) platform that is designed to support business processes such as sales, marketing, and customer service. As a multitenant cloud, Salesforce allows multiple customers to share the same resources of its application server. This means that each customer's data is stored separately but all customers share the same underlying infrastructure and application code.

In conclusion, Salesforce's multitenant cloud architecture and Fair Usage Policy are designed to ensure that all customers have access to reliable and efficient resources. By setting System Resource Thresholds, Salesforce can maintain the performance and availability of its platform while also ensuring that its customers are using its resources in a fair and responsible manner.

# Bulkification
## Best Practices for Processing Multiple Records in Salesforce

### 1. Consume the least amount of resources
When processing multiple records, try to minimize the amount of memory and CPU usage by optimizing your code. Use efficient algorithms and avoid unnecessary calculations and operations that consume resources.

### 2. Reduce the chances of hitting governor limits
Governor limits are the limits on the amount of resources that your code can consume in Salesforce. When processing multiple records, be mindful of these limits and try to reduce the chances of hitting them. For example, if you are processing a large number of records, consider batching them to avoid reaching the limit on the number of records that can be processed in a single transaction.

### 3. Reduce transaction execution time
When processing multiple records, aim to reduce the time it takes for your code to execute. This can be achieved by minimizing the number of SOQL queries and DML statements you use. Instead, try to use bulk DML operations and aggregate queries to process multiple records at once.

### 4. Never write SOQL queries and DML statements in loops
Writing SOQL queries and DML statements in loops can result in hitting governor limits quickly. Instead, collect the required data in a single query and update records using bulk DML operations. This will not only reduce the chances of hitting limits, but also improve performance by reducing the number of database round-trips.


## Salesforce CPU Time Exception
Salesforce has certain limits on the amount of resources that can be consumed by Apex code. One such limit is the CPU time limit, which is the maximum amount of CPU time that a single transaction can consume. If this limit is exceeded, Salesforce will throw a CPU Time Limit Exceeded exception.

This exception occurs when the total CPU time used by the Apex code exceeds the allowed CPU time for the transaction. The allowed CPU time is determined by the number of Apex code statements executed in the transaction, as well as the complexity of those statements.

To avoid this exception, it is important to optimize your Apex code and reduce its CPU time consumption. Here are some tips to help you avoid CPU time limit exceptions:

### 1. Limit the amount of data being processed
Reducing the amount of data being processed can help to reduce the CPU time consumption. Try to filter out unnecessary data and use selective queries to retrieve only the required data.

### 2. Use efficient algorithms and data structures
Using efficient algorithms and data structures can help to minimize the number of operations required to process data. For example, using sets and maps can help to eliminate duplicate records and reduce the time needed for data lookups.

### 3. Reduce the number of SOQL queries and DML statements
Using bulk DML operations and aggregate queries can help to reduce the number of SOQL queries and DML statements needed to process data. This can significantly reduce CPU time consumption.
### 4. Avoid recursive triggers and infinite loops
Recursive triggers and infinite loops can cause CPU time consumption to skyrocket. Make sure to use recursion check mechanisms and always test your code for such scenarios.


## Limits Class in Salesforce
Salesforce imposes certain limits on the amount of resources that Apex code can consume, such as CPU time and memory usage. To help developers work within these limits, Salesforce provides the Limits class, which can be used to retrieve information about the current limits and the limits that have been set for the organization. Here are some methods available in the Limits class:
### 1. getDMLStatements()
This method returns the number of DML statements (such as insert, update or the database.EmptyRecycleBin method) that have been called in the current transaction.

### 2. getHeapSize()
This method returns the approximate amount of memory (in bytes) that has been used for the heap in the current transaction.

### 3. getLimitDMLStatements()
This method returns the total number of DML statements or the database.EmptyRecycleBin methods that can be called in the current transaction.

### 4. getLimitHeapSize()
This method returns the total amount of memory (in bytes) that can be used for the heap in the current transaction.

Using these methods, developers can keep track of the resource consumption in their Apex code and avoid hitting the limits set by Salesforce. Here's an example of how to use these methods in Apex code:
```apex
List<Account> accounts =[SELECT Id, Type, Name, ParentId FROM Account];
//endless while loop
while(1==1){
    if(Limits.getHeapSize()*2 >= Limits.getLimitHeapSize()){
        break;
    }
    // make copy of accounts list
    List<Account> dupAcc = accounts;
    // add copy to original list
    accounts.addAll(dupAcc);
}
System.debug('List size: '+accounts.size());
```
In this example, the code continuously adds copies of the same list to itself until it hits the heap size limit. The getHeapSize() method is used to check the current heap size, while the getLimitHeapSize() method is used to check the heap size limit. Once the heap size limit is reached, the while loop breaks and the size of the final list is printed using System.debug().
