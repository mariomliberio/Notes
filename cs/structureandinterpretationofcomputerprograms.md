# cs 61 Uc Berkley

### Lecture 1 Functional Programming.

**Disclaimer: These lectures follow the book Structure and Interpretation of Computer Programs**

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

-  