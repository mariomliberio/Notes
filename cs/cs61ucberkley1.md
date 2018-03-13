# scheme dialect lisp

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

- Let's combine a few of those