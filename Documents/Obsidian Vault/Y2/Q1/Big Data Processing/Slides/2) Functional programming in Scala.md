
Function signature:

foo(x: \[A\], y: B) -> C

Function foo takes as arguments a traversable type A and a type B and returns a parameter with type C

Foo : function name
X, y : function arguments
\[A\], B : types of function arguments
-> : denotes the return type
C : type of return result
\[A\] : denotes that A can be traversable

  

### !!! FP is side effect free
- It should not have loops (recursion is allowed)
- It should not modify the state of something outside the scope (i.e. changing variables values)

  

### Side effects
- Modifying a variable
- Modifying a data structure in place: In FP, data structures are always persistent.
- Setting a field on an object: OO is not FP!
- Throwing an exception or halting with an error: In FP, we use types that encapsulate and propagate erroneous behavior
- Printing to the console or reading user input, reading writing to files or the screen: In FP, we encapsulate external resources into Monads.

  

  

#### Referential transparency: 
A function needs to always return the same thing given the same data (usually done by not using global variables)

  

:: = list concatenation
Example : List(1, 2, 3, 4, 5) = 1 :: 2 :: 3 :: 4 :: 5 :: Nil
Nil = empty list

  

### Functions:

- map(list\[A\], f: A => B) : list\[B\] = applies the functions to all elements in a list
- flatMap(list\[A], f: A => \[B]) : list\[B] = like map, but flattens the result to a single list
- foldL(list\[A], f: (B, A) => B, B) : B = takes f of the 2 arguments and an init value and combines the elements by applying f on the result of each previous application. (Eg. Reduce)
- GroupBy(
- Filter(
- scanL(
- Zip(

  

Laziness = delays the evaluation of an expression until its value is needed

### Monads 
= design pattern that defines how functions can be used to build generic types

*Monads are typically used for dealing with side effects by capturing them

Can be used for :
- Null points : Option\[T] -> wraps the value that may be null or undefined. Can be either of some type \[A] or None, when the value is undefined
- Exceptions : Try\[T] -> wraps a computation that may result in an exception, or return a successfully computed value. Can be either Success\[A] for a type A result or Failure\[E] for an error of type E
- Latency in asynchronous actions : Future\[T] (like promises in js)