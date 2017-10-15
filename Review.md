# Some basic review of the language

* [Value Types](#value-types)
   * [Struct](#struct)
* [Reference Type](#reference-types)
* [Garbage Collection](#garbage-collection)
  * [Generation 0](#generation-0)
  * [Generation 1](#generation-1)
  * [Generation 2](#generation-2)
   


## Value Types

- The value types are divided into 2 subtypes: Enummeration and Struct
- They are stored in an area of memory called stack.
- After the execution of the value type declararion the value is discarded from the stack.

### Struct
  - A struct is a value type that is used to encapsulate small groups of information.
  - It is possible to have constants, properties and methods inside a struct (but it is not recomended)
  - It is a good idea to override the Equals method, becaus the original one was made to be generic, so it will use reflection to compare all the values inside a struct

## Refence Types
- String is a reference type.
- They are storead in an area of memory called "heap".
- They have a reference to the heap and if assign a reference type to another, the reference will be the same.
- The heap it's only cleaned when the Garbage collection determines it is no longer needed.

##Garbage Collector
- The .NET's garbage collector manages the allocation and release of memory for your application
- It enables you to develop your application without having to free memory
- The managed heap is divided in some generations

###Generation 0
 - This is the youngest generation and contains the newly created objects. 
 - Has short-lived objects and collected frequently.
 - The objects that survive the Generation 0 are promoted to Generation 1.
 - Example : A temporary object.
 
###Generation 1
 - This generation contains the longer lived objects that are promoted from generation 0. 
 - Basically this generation serves as a buffer between short-lived objects and longest-lived objects. 
 - The objects that survive the Generation 1 are promoted to Generation 2. 

###Generation 2
 - This generation contains the longest lived objects that are promoted from generation 1 and collected infrequently.
 - Example : An object at application level that contains static data which is available for the duration of the process. 
