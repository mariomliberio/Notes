# PHP THE RIGHT WAY

### Chapter 4: Language Highlights.

**Programming Pardigms**

- PHP is a flexible and dynamic language that supports a variety of programming techniques.

*Object-oriented Programming*

- Very complete set of object-oriented programming features including support for classes, abstract classes, interfaces, inheritance, constructors, cloning, exceptions ++.

*Functional Programming*

- PHP supports first class functions, therefore a function can be assigned to a variable.
- Both user-defined and built-in functions can be refereced and be invoked dynamically by a variable.
- Functions can be passed as arguments to other functions  (called High-order functions** and functions can return other functions.
- Recursion is supported however most php code is focused on iteration.
- Anonymous functions are also present since 2009.
- PHP 5.4 added the ability to bind closures to an object's scope and also improved support for callables for interchangability with anonymous functions.

*Meta Programming*

- PHP supports various forms of meta-programming through mechanisms like the reflection API and Magic Methods available like __get() , __set() , __clone(), __toString() , __invoke(** etc. These allow developers to hook into class behaviour.

*Namespaces*

- PHP community has a lot of devs creating lots of code. This means that one library's PHP code might use the same name for a class as another. When both libraries run on the same namespace, they will collide and cause trouble.
- *Namespaces* solve this problem. 
