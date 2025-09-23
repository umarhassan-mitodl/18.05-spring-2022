---
content_type: page
description: This page includes a short tutorial to explain 'for loops'.
draft: false
title: 'R Tutorial: For Loops'
uid: 8321e26a-a623-43e0-963c-0e5faf60910e
---
This is a short tutorial to explain 'for loops'.

## Color Coding

\# Comments are in maroon      
Code is in black      
Results are in this shade of green    

## rep()

\# Often we want to start with a vector of 0's and then modify the entries in later code. R makes this easy with the replicate function rep() 

\# rep(0, 10) makes a vector of of 10 zeros. 

```plaintext
x = rep(0, 10) 
print(x) 
[1] 0 0 0 0 0 0 0 0 0 0 
```

\# rep() will replicate almost anything 

```plaintext
x = rep(2, 6) 
print(x) 
[1] 2 2 2 2 2 2 

x = rep('abc', 5) 
print(x) 
[1] "abc" "abc" "abc" "abc" "abc" 

x = rep(1:4, 5) 
print(x) 
[1] 1 2 3 4 1 2 3 4 1 2 3 4 1 2 3 4 1 2 3 4    
```

## for(i in x)

\# 'for loops' help us loop, i.e. repeat, through the elements in a vector and run the same code on each element 

\# We will illustrate with examples 

\# Loop through the sequence 1 to 5 printing the square of each number 

```plaintext
for (j in 1:5) {
  print(j^2) 
} 
[1] 1 
[1] 4 
[1] 9 
[1] 16 
[1] 25 
```

\# We can capture the results of our loop in a list     
\# First we create a vector and then we fill in its values 

```plaintext
n = 5&nbsp; 
x = rep(0,n)&nbsp; 
for (j in 1:n) { 
  x[j] = j^2 } 
print(x) 
[1]  1  4  9 16 25 
```

\# You always wanted to know the sum of the first 100 squares. 

```plaintext
n = 100 
x = rep(0,n) 
for (j in 1:n) {
  x[j] = j^2 
} 
s = sum(x) 
print(s) 
[1] 338350 
```

\# Let's use a for loop to estimate the average of squaring the result of a roll of a die. 

```plaintext
nsides = 6 
ntrials = 1000 
trials = rep(0, ntrials) 
for (j in 1:ntrials) {
  trials[j] = sample(1:nsides, 1)  # We get one sample at a time 
} 
m = mean(trials^2) 
print(m) 
[1] 15.207 
```

\# Of course we could have done this simulation without a loop, but this illustrates for loops. 

\# for loops are truly valuable when the calculation is more complicated and we can't do it exactly or with built in R functions. 

\# Let's estimate the probability of a derangement in a permutation of 9 objects. (A derangement is a permutation where no element ends up in its original position.) 

```plaintext
n = 9 
x = 1:n 
ntrials = 10000 
trials = rep(0, ntrials) 
for (j in 1:ntrials) {
    y = sample(x, n)
    s = sum(y == x)  # s = number of people in their original seat
    trials[j] = (s == 0) # 1 if a derangement, 0 if not 
} 
m = mean(trials)  # mean(trials) = fraction that are 1's 
print(m) 
[1] 0.3697
```