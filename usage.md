# Example usages

```bash

# show diff
:window diff

# go to beginning of next method
:[count]]m    



```


+ Operators
```bash

w   jump by start of words (punctuation considered words)
W   jump by words (spaces separate words)
e   jump to end of words (punctuation considered words)
E   jump to end of words (no punctuation)


```

+ Text objects
```bash

| aw | a word | 



```

+ Motions
```bash
# help motion.txt
| [count]+ | down to first non-blank char of line |
| [count]f/F {char} | to next occurence of { char } including | 
| [count]t/T {char} | to before next occurence of { char } excluding |

```


# Putting it all together

