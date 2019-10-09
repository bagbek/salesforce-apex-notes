# 1. **List Datatype**
**NOTE:** List index starts from 0.  List is an ordered collection.

`List<Integer> rollNumbers = new List<Integer>{11008890, 11008100, 11007231};`
`System.debug(rollNumbers);` // (11008890, 11008100, 11007231)

`rollNumbers.add(89897767);`
`rollNumbers.add(89897764);`
`rollNumbers.add(89897765);`

`System.debug(rollNumbers);` // (11008890, 11008100, 11007231, 89897767, 89897764, 89897765)

## get item on index 1
`Integer rollNum = rollNumbers.get(1);`
`System.debug(rollNum);` // 11008100

**NOTE:** short way to write a code
`System.debug(rollNumbers.get(1));` //11008100


## add item on index 4
`rollNumbers.add(4, 99990000);`
`System.debug(rollNumbers);` // (11008890, 11008100, 11007231, 89897767, 99990000, 89897764, 89897765)

## get the list size -it shows how many items in it
`System.debug(rollNumbers.size()); ` // 7

## remove the item on index 3
`rollNumbers.remove(3); `
`System.debug(rollNumbers);` // (11008890, 11008100, 11007231, 99990000, 89897764, 89897765)

`System.debug(rollNumbers.size());` // 6

## update item on index 1
`rollNumbers.set(1, 44444444);`
`System.debug(rollNumbers);` // (11008890, 44444444, 11007231, 99990000, 89897764, 89897765)

## clear the list
`rollNumbers.clear();`
`System.debug(rollNumbers);` // {}
`System.debug(rollNumbers.size());` // 0

## below line will throw an error
`rollNumbers.set(1, 44444444);`
`System.debug(rollNumbers);`



# 2. **Set Datatype**
**NOTE:** It directly stores your data without the indexes. So, that's why we call it unordered collection of elements. The most important property of a set is, it doesn't allow Duplicate Data. Unlike list, set doesn't have any indexes. It simply stores your data as it is without any indexes. And if you want to get an item, it will directly get it by its value. So, in list, we used to get an item by its index. 

`Set<Integer> rollNumbers = new Set<Integer>{11008890, 11008100, 11007231};`
`System.debug(rollNumbers);` // {11007231, 11008100, 11008890}

`rollNumbers.add(89897767);`
`rollNumbers.add(89897764);`  
`rollNumbers.add(89897765);` 

`System.debug(rollNumbers);` // {11007231, 11008100, 11008890, 89897764, 89897765, 89897767}

## adding duplicate values - NOT ALLOWED
`rollNumbers.add(89897767);`
`System.debug(rollNumbers);` // {11007231, 11008100, 11008890, 89897764, 89897765, 89897767}

## check if set has an item (contains - true or false)
`System.debug(rollNumbers.contains(89897764));` // true
`System.debug(rollNumbers.contains(345345));`

## delete an item
`rollNumbers.remove(89897765);`
`System.debug(rollNumbers);` // false

## get set size
`System.debug(rollNumbers.size());` // 5

## check if set is empty (isEmpty - true or false)
`System.debug(rollNumbers.isEmpty());` // false

## remove all items
`rollNumbers.clear();`
`System.debug(rollNumbers.isEmpty());` // true



# 2. **Map Datatype**
**NOTE:** It stores the data in a key value pair.

Map<Integer, String> class2020 = new Map<Integer, String>();

## add a new student/item.   
**NOTE:** to add a new item in a map, we need to use the **'put'** method. In the set and list, we use the **'add'** method.

`class2020.put(11008890, 'Smith');`
`System.debug(class2020);` //{11008890=Smith}

`class2020.put(11008891, 'Harry');`
`class2020.put(11008892, 'Rick');`
`class2020.put(11008893, 'Bill');`

`System.debug(class2020);` // {11008890=Smith, 11008891=Harry, 11008892=Rick, 11008893=Bill}

`class2020.put(11008894, 'Bill');`
`System.debug(class2020);` // {11008890=Smith, 11008891=Harry, 11008892=Rick, 11008893=Bill, 11008894=Bill}

## update/override value
`class2020.put(11008894, 'Skywalker');`
`System.debug(class2020);` // {11008890=Smith, 11008891=Harry, 11008892=Rick, 11008893=Bill, 11008894=Skywalker}

## get a value
`System.debug(class2020.get(11008892));` // Rick

## remove an item from map
`class2020.remove(11008893);`
`System.debug(class2020);` // {11008890=Smith, 11008891=Harry, 11008892=Rick, 11008894=Skywalker}

## get all the keySet
`Set<Integer> rollNumber = class2020.keySet();`
`System.debug(rollNumber);` // {11008890, 11008891, 11008892, 11008894}

## get all the values
`List<String> students = class2020.values();`
`System.debug(students);` // (Smith, Harry, Rick, Skywalker)

## check if map has the key
`System.debug(class2020.containsKey(11008892));` // true

`System.debug(class2020.containsKey(11008893));` // false



# Challenge
## posts for apple category
`List<String> applePosts = new List<String>{'Demystifying ios Collections', 'Datatypes and variables in IOS'};`
## posts for lightning category
`List<String> samsungPosts = new List<String>{'Events in android framework', 'Developing reusable components'};`

## map to store the categories and post lists
`Map<String, List<String>> allPosts = new Map<String, List<String>>();`

## insert apex posts
`allPosts.put('Apple', applePosts);`
// insert lightning posts
`allPosts.put('Samsung', samsungPosts);`

## printing all posts along with categories
`System.debug(allPosts);` // {Apple=(Demystifying ios Collections, Datatypes and variables in IOS), Samsung=(Events in android framework, Developing reusable components)}