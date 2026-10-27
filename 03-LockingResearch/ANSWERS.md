# Assignment 03 — Answers

Student name: Saif El-Den Nasr
Group / ID: Group 3

1. it is a .net class which used to synchronize access to shared resources when multiple threads execute concurrently

2. It is compiled to exception-safe code using try/finally structure by using Monitor.Enter() to acquire the lock and Monitor.Exit() to release it

3. lock                                 Monitor APIs
1- Concise and easy to read             More Complex and requires explicit methods calls
2- Automatically releases the lock      You must ensure that the lock released correctly (By try/finally)
   through compiler-generated 
   exception-safe handling 

4. Wait, Pulse and PulseAll must be used with the appropriate monitor lock held by the calling thread. A Notification doesn't gurantee that the condition is satisfied. The waiting thread must check the condition again after reacquiring the lock.

5. Using lock:-
    private readonly object _lock = new();
    private int _counter;

    public void Increment()
    {
        lock (_lock)
        {
            _counter++;
            Console.WriteLine(_counter);
        }
    }

- Using Monitor:-
    private readonly object _lock = new();
    private int _counter;

    public void Increament()
    {
        object @lock = _lock;
        bool lockTaken = false;
        try
        {
            Monitor.Enter(@lock, ref lockTaken);
            _counter++;
            Console.WriteLine(_counter);
        }
        finally
        {
            if(lockTaken)
            {
                Monitor.Exit(@lock);
            }
        }
    }

Links:

- https://learn.microsoft.com/en-us/dotnet/api/system.threading.monitor?utm_source=chatgpt.com
- https://learn.microsoft.com/en-us/dotnet/api/system.threading.monitor.enter?view=net-10.0&utm_source=chatgpt.com
