#CS 61 UC BERKLEY LECTURE 1 FUNCTIONAL PROGRAMMING
#### scheme dialect of lisp

- Prefix notation for procedures: 
```
(* 25 4 12)
1200

(+ 21 35 12 7)
75
(+ (* 3 (+ (* 2 4) (+ 3 5))) (+ (- 10 7) 6))
57
```

- Printing words will give error, however using ``` ' ``` in front of whatever will print that:
```
hello
> error
'hello
> hello
```

- Different functions such as ```first, last, butfirst, butlast, word, sentence```:

```
(first 'hello)
> h
(last 'hello)
> o
(butfirst 'hello)
> ello
(butlast 'hello)
> hell
(word 'now 'here)
> nowhere
(sentence 'now 'here)
> (now here)
```
- We can also abbreviate these operators eg. ``` butfirst -> bf , butlast -> bl , sentance -> se ```.

- Taking the sentence example from above, calling ```(now here)``` would just call a function named ```now``` with the argument ```here```.  If we actually want a sentence we would do as so: ``` '(magical mystery tour)```. This would be the same for a ```word```.

- Let's combine a few of those notions
```
(first '(the fool on the hill))
> the

(bf '(the fool on the hill))
> fool on the hill
```

- These functions can also be composed
```
(first (bf '(a hard days night)))
> hard
```

- Lets explain the last example: ```butfirst``` of ```'a hard days night``` is ```hard days night``` and first of this is ```hard```. Pretty simple so far. 

- Let's go even one layer deeper:
```
(first (first (bf '(she loves you))))
> l
```
- Our ```bf``` removes ```she```, then ```first``` of ```'loves you``` is ```loves``` and first of ```loves``` is ```l```. 

***

**Naming and environment**

- ```define``` used in lisp to give names to variables, its the simplest method of abstraction. 
```
(define (square x)
    (* x x))
> square

(square (+ 2 3))
> 25
```

- First ```(+ 2 3)``` equals 5 and our defined ```square``` will multiply the argument by itself, in this case 5 * 5, therefore 25 is returned. 
- ```define``` is the *keyword* , the expression we gave it is a *special form*.
- Another example:
```
(define hello (+ 2 3))
> hello

hello
> 5
```
- There is about a dozen of *special forms* in the Scheme dialect of Lisp.

- Let's look back at our previous ```define square``` and split its components one by one.
```
(define (square x)
    (* x x))
(square (+ 2 3))
```
- Our first ```x``` is the *formal parameter* . It is the name for an argument to a function. ```(* x x)``` is the body. These two are part of the definition of a function. ```(+ 2 3)``` is the *actual argument expression* . The *actual argument value* is ```5``` which is invisible but is the result of the *actual argument expression* .

- Let's look at another example:
```
(define (plural wd))
    (word wd 's)
> plural

(plural 'computer)
> computers

(plural 'book)
> books

(plural 'boy)
> boys
```

- In our ```'boy``` example; ```'boy``` is the *actual argument expression* while ```boy``` is the *actual argument value*. ```wd``` is our formal parameter, we don't use word for that because it is a primitive function. 

- However we can run into problems by doing this:
```
(plural 'fly)
> flys
```
- ```flys``` doesn't mean anything in english, therefore were gonna have to add a condition to fix this. To do this were gonna use an ```if``` statement, an ```equal?``` *predicate function*, this is a function that returns a boolean. Predicates usually end in a question mark. 
```
(define (plural wd)
    (if (equal? (last wd) 'y)
    (word (bl wd) 'ies)    // bl --> butlast (all but the last letter)
    (word wd 's)))
> plural

(plural 'book)
> books

(plural 'fly)
> flies

(plural 'boy)
> boies // we have broken boy... How would we fix this?
```