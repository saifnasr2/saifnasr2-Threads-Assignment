# Assignment 02 — Answers

Student name: Saif El-Den Nasr
Group / ID: Group 3

## What is wrong

- There was a race condition because many threads can work on the method at the same moment, read and modify the shared counters concurrently so it can make lost data and inaccurate results.

## How you fixed it

- I used lock to prevent many threads do the same work at the same moment , but just one thread can do the work and the other threads wait it until it finish then the next thread can do its work and that prevent the race condition.

# Output Before
    Customer-40 booked a table. Left=-2
    Customer-31 booked a table. Left=-2
    Customer-38 booked a table. Left=-2
    Customer-28 booked a table. Left=-2
    Customer-33 booked a table. Left=-2
    Customer-30 booked a table. Left=-2
    Customer-29 booked a table. Left=-2
    Customer-35 booked a table. Left=-2
    Customer-07 booked a table. Left=-2
    Customer-36 booked a table. Left=-2
    Customer-26 booked a table. Left=-2
    Customer-37 booked a table. Left=-2
    Customer-09 booked a table. Left=-2
    Customer-27 booked a table. Left=-2
    Customer-25 booked a table. Left=-2
    Customer-34 booked a table. Left=-2
    Customer-24 booked a table. Left=-2
    Customer-23 booked a table. Left=-2
    Customer-39 booked a table. Left=-2
    Customer-32 booked a table. Left=-2
    Customer-22 booked a table. Left=-2
    Customer-21 booked a table. Left=-2
    Customer-20 booked a table. Left=-2
    Customer-18 booked a table. Left=-2
    Customer-16 booked a table. Left=-2
    Customer-14 booked a table. Left=-2
    Customer-19 booked a table. Left=-2
    Customer-17 booked a table. Left=-2
    Customer-15 booked a table. Left=-2
    Customer-13 booked a table. Left=-2
    Customer-12 booked a table. Left=-2
    Customer-11 booked a table. Left=-2
    Customer-10 booked a table. Left=-2
    Customer-08 booked a table. Left=-2
    Customer-06 booked a table. Left=-2
    Customer-04 booked a table. Left=-2
    Customer-05 booked a table. Left=-2
    Customer-03 booked a table. Left=-2
    Customer-01 booked a table. Left=-2
    Customer-02 booked a table. Left=-2

    Booked=1, TablesLeft=-2

# Output After
    Customer-02 booked a table. Left=4
    Customer-04 booked a table. Left=3
    Customer-07 booked a table. Left=2
    Customer-06 booked a table. Left=1
    Customer-05 booked a table. Left=0

    Booked=5, TablesLeft=0