# Assignment 05 — Answers

Student name: Saif El-Den Nasr
Group / ID: Group 3

## Failures you observed

- using dictionary for view counting and queue for email jobs is not safe thread so multiple threads access them concurrently and this can cause race conditions and incorrect view counts.

- Checking EmailJobs.Count before Dequeue() is not atomic, so a worker may attempt to dequeue from an empty queue and throw an InvalidOperationException

## What you changed

- I replaced Dictionary with ConcurrentDictionary and used AddOrUpdate to update view counts safely.
- I replaced Queue with ConcurrentQueue and used TryDequeue() to retrieve and remove email jobs atomically.

## Collection safety vs business-rule safety

- Thread-safe collections protect their individual operations, but they do not automatically make an entire business operation thread-safe. for example, ConcurrentQueue makes enqueue and dequeue safe when multiple threads use the queue, but checking the count and then dequeue separately is still not an atomic sequence. Using TryDequeue() avoids that problem. similarly, ConcurrentDictionary supports concurrent updates, while AddOrUpdate() handles the counter update safely
