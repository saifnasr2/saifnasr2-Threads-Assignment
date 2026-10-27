# Assignment 04 — Answers

Student name: Saif El-Den Nasr
Group / ID: Group 3

## Why Expected and Actual disagree

- Because the operation Views++ is not atomic and it may more than one thread update it at the same moment because it is a shared data between all threads

## What you changed

- I made the operation atomic by using Interlocked class

## When would you protect the update differently

- when i need to handle several related variables and put restrict conditions i can use lock rather than InterLocked.
