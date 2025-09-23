---
content_type: page
description: This page includes a tutorial about write your own functions.
draft: false
title: 'R Tutorial: Functions'
uid: 0b200191-a15a-4922-912e-d8713eafef15
---
## Time

We estimate this tutorial will take 10 minutes. It consists of two simple examples of writing functions.

## Write your own functions

\# R has many built in functions like `sin(x), exp(x), print(s)`. Generally speaking, you won't write functions on the command line. Rather, they will be put in source files, or in the source pane in R Studio.    
\# Here we will give two simple examples of writing our own function.

\# You should paste this code into the source window and then choose 'Source' under the 'Code' menu. Then practice

#Here's a simple function that squares its argument. 

```plaintext
square_me = function(n) {    
    x = n*n    
    return(x) 
} 
```

\# Now you can call this function from the command line 

```plaintext
> square_me(4) 
 [1] 16 
```

Here's a function that builds and prints a phrase from some input strings. 

```plaintext
hello_there = function(name, adjective) {     
    phrase = paste("Hello ", name, "! You look ",                     
                    adjective,".", sep="")     
    print(phrase)  
} 
> hello_there("Jerry", "fuzzy")  
 [1] "Hello Jerry ! You look fuzzy ."
```