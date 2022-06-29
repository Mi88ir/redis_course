# Basic String Commands

Redis can store data in a mapping of keys to values.

>**Instructions to understand commands.**
>1. A capitalised word you see is a keyword
>2. A lowercase word is a value that is to be edited/replaced
>3. Square brackets or [] refer to arguments that are optional
>4. Pipe symbol or | refers to the OR operation

<br>

### **SET & GET**
<br>

Set and Get commands are mainly used for storing plain numbers and strings in the database. 

For SET -

```
//Syntax for SET

SET key value

//Example

SET message "Hello World" //Output: "OK"
```

For GET -

```
//Syntax

GET key

//Example

GET message //Output: "Hello World"
```

<hr>

Optional Arguments

```
EX/PX/EXAT/PXAT/KEEPTTL - Options for when the value should  expire

NX/XX - Options for setting values based on key exists or not
```
<hr>

### **NX | XX** 

<br>

For NX - a value is set if the key does not already exist in the database

```
SET name "John" NX

//result will return OK if no key 'name' exists in database else will return null
```

For XX - a value is set if the key does already exist in the database

```
SET name "John" XX

//result will return OK if key already exists in database else will return null
```
<hr>

### **EX/PX/EXAT/PXAT/KEEPTTL** 

Redis servers as a memory based database service. So in order to understand why we need expiration, we take the following example.

Usually when an application makes a request for the data, we need to be able to pass data quickly in response. The setup with Redis is such that it may temporarily hold data for some time as a copy from the main database like MongoDB or Postgresql and allow quick data access. After a certain time if the data is not accessed, then the copy of the data can be removed from the Redis cache and the memory freed up.

<br>

For EX - 

```
SET color red EX 2

//EX 2 - automatically delete this value after 2 SECONDS
```

<br>

For PX - 

```
SET color red PX 2000

//PX 2000 - automatically delete this value after 2000 milliseconds
```

<br>

For EXAT/PXAT - Allows you to specify a particular date time

For KEEPTTL - Keep any expiration that has been already applied to key