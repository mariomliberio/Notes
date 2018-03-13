# Notes of Structure And Interpretation of Computer Programs

- This book is available at mitpress.mit.edu for free, just google it.

***

**The elements of programming**

- Every powerful language has three mechanisms for combining simple ideas into more complex ideas:
    1. Primitive Expressions: Represent the simplest entities the language is concerned with.
    2. Means of Combination: By which compound elements are built from more simpler ones.
    3. Means of Abstraction: By which compound elements can be named and manipulated as units.

- In programming we deal with two kinds of elements:
    1. Procedures: Informally, descriptions of the rules for manipulating data.
    2. Data : Informally, stuff that we want to manipulate.

- Any powerful programming language should be able to describe primitive data and primitive procedures and should have methods to combine and abstract these procedures and data.

***

**Expressions**

- Lets examine interactions with an interpreter of the Scheme dialect of Lisp. You type an *expression* and the interpreter responds by evaluating that expression. 

- One type of primitive expression would be a number. 

- If you present Lisp with a number, lets say *486* , the interpreter will respond by printing *486*.

- Expressions representing numbers, may be combined with expressions representing a primitive procedure, such as + (addition) or * (multiplication) to form a *compound expression*. For Example:
```
(+ 137 349)
486

(- 1000 334)
666

(* 5 99)
495

(/ 10 5)
2

(+ 2.7 10)
12.7
```

- Expressions such as these, presented within parethesis to denote procedure application, are called *combinations*.

- The leftmost element (+ - * /) is called the *operator* . The other elements (137 349 1000 334...) are called *operands*.

- The value of these combinations are obtained by applying the procedure specified by the operator, to the arguments which are the values of the operands.

- This convention in Lisp of applying the operator to the left of the operands is called *prefix notation*. While this might seem counterintuitive, it allows us to create procedures which may take an arbitrary number of arguments such as:
```
(* 25 4 12)
1200

(+ 21 35 12 7)
75
```
- This avoids ambiguity as the operator is always on the left, and the whole combination is between parenthesis.

- A second advantage of prefix notation is that it allows combinations to be nested in a straightforward fashion as so:
```
(+ (* 3 5) (- 10 6))
19
```
- These are called *compositional functions*.

- There is no limit to the depth of nesting and the overall complexity of expressions our Lisp interpreter can evaluate. For example the following would seem quite complicated to a human (even though it is basic algebra):
```
(+ (* 3 (+ (* 2 4) (+ 3 5))) (+ (- 10 7) 6))
57
```

- Even with a slightly more complicated expression like this one or a much more complicated one, the interpreter always acts in the same way, it reads it from our terminal, evaluates it and prints the result. This is often called a *read-eval-print-loop*.

***

**Naming and the Environment**

-  A critical aspect of any programming language is the means used to give names to refer to computational objects. We say that the name identifies a *variable* whose *value is the object*

- In the scheme dialect of Lisp, we name things with ```define```. For example:
```
(define size 2)
```
- This makes the interpreter associate the value 2 with the name ```size```. Once this association has been made, we can refer to the value 2 by the name ```size```:
```
size
> 2
(* 5 size)
> 10

(define pi 3.14159)
(define radius 10)
(* pi (* radius radius))
> 314.159
```
- In the ```pi``` ```radius``` example we first multiply ```radius * radius``` therefore 10 * 10 = 100, and then we multiply this by ```pi``` therefore the interpreter returns 314.159.

- Here is another example, building on the previous (therefore ```pi``` = 3.14159 and ```radius``` = 10:
```
(define circumference (* 2 pi radius))
circumference
> 62.8318
```
- When we call ```circumference``` it is multiplying ```pi``` by ```radius``` and by ```2``` therefore it returns 62.8318.

- ```Define``` is our languages simplest method of abstraction. It allows us to use simple names to refer to the result of compound operations. 

- Computational objects may have very complex structures, and it would be inconvenient to have to remember all the details and repeat them everytime we want to use them. Complex programs are built by building, step by step, computational objects of increasing complexity. These name-object associations can be created incrememntally in succesive interactions. This encourages incremental develpment and testing of programs and is largely responsible for programs consisting of a large number of simple procedures. 

- In order to associate values with symbols and reusing them, the interpret must mantain some sort of memory that keeps track of name-object pairs. This is called the *environment* ( more precisely the *global environment*, since a computation may involve a number of different environments)

***

**Evaluating Combinations**

-  