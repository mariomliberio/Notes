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

-  One of our goals in this first chapter is to isolate issues about thinking procedurally. When evaluating combinations, the interpreter follows a procedure.

- To evaluate a combination, do the following:
    1. Evaluate the subexpressions of the combination
    2. Apply the procedure that is the value of the leftmost subexpression (the operator) to the arguments which are the values of the other subexpressions (the operands).

- This simple rule illustrates some important points about processes. First, the first step dictates that in order to accomplish the evaluation process for a combination we must first evaluate each element of the combination. This the evaluation is *recursive* in nature, it includes as one of its steps, the need to invoke the rule itself. 

-  The idea of recursion, can easily express what would seem rather complex in a deeply nested combination. For example:

```
(* (+ 2 (* 4 6))
    (+ 3 5 7))
```

- Here, the evaluation rule has to be applied to four different combinations. If we represent this visually it looks like so:
 ![Figure 1.1](images/strcpfigure1-1.gif).
 
 - Each combination is represented by a node with branches corresponding to its operators and operands. The terminal nodes, those who have no branches coming from them are either operators or numbers. The value of the operands move upwards, starting from therminal nodes and combining at higher and higher levels. Soon enough, we shall see that recursion is a powerful technique for dealing with hierarchical tree-like objects. This type of upwards progression in the evaluation rule is an example of a process known as *tree accumulation*.

 - Before evaluating combinations, we have to evaluate primitive expressions. We take care of these cases by stipulating that:
    - Values of numerals are the numbers they name.
    - Values of built-in operators are the instruction sequences that carry out the operations.
    - Values of other names are objects associated with those names in the (global or local) environment. 

- We could look at the second rule as a special case of the third one because symbols such as ```+``` or ```*``` are objects built in the global environment. 

- The key point to notice here is the role of the environment in determining the meaning of symbols in expressions.

- In an interactive language like Lisp, it is meaningless to speak of an expression such as ```(x + 1)``` without specifying information about the meaning of ```x``` in our working environment.  

- Note that the evaluation rule given above, does not handle definitions. Eg. evaulating ```(define x 3)``` does not apply ```define``` to two arguments, one being the value of the symbol ```x``` and the other ```3``` since the purpose of ```define``` is precisely to associate ```x``` with a value, in this case ```3```. In short ```(define x 3)``` is not a combination. 

- These exceptions are called *special forms*. ```define``` is the first example of a special form that we have looked at but there are a few more.

- Each special form has its own unique evaluation rule.  These expressions and their associated evaluation rule constitute the *syntax* of the programming language. In comparaison to other languages, Lisp has very simple syntax, therefore it is a good usecase to learn the basics of programming.  

***

**Compound Procedures**

- 