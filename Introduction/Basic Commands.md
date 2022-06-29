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

Optional Arguments

```
EX/PX/EXAT/PXAT/KEEPTTL - Options for when the value should  expire

NX/XX - Options for setting values based on key exists or not
```
<br>

### **NX | XX**

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