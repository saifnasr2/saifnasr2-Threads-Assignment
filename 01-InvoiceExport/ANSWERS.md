# Assignment 01 — Answers

Student name: Saif El-Den Nasr
Group / ID: Group 3

## Problems with the current design

- The Problem that the methods which load order, read customer, write invoice are synchronous and they use methods like Threads.Sleep(), File.WriteAllText() and File.ReadAllText() which block the thread until this operation finished and this slows the app.

## What you changed

- I modified all the methods to be asyncronous and replaced the sync methods by async methods like Task.Delay(), File.WriteAllTextAsync() and File.ReadAllTextAsync() which release the thread to make another work until this operation finishes and this made the app more faster and can handle multi orders faster.

## Before Modification
OutPut:-
    Starting invoice export...
    Customer files: d:\Programming\c# projects\AdvancedCsharp-Assignment-01-InvoiceExport\InvoiceExport\bin\Debug\net9.0\Data
    Invoice output: d:\Programming\c# projects\invoices

    Wrote d:\Programming\c# projects\invoices\invoice-1001.txt
    Wrote d:\Programming\c# projects\invoices\invoice-1002.txt
    Wrote d:\Programming\c# projects\invoices\invoice-1003.txt
    Wrote d:\Programming\c# projects\invoices\invoice-1004.txt
    Wrote d:\Programming\c# projects\invoices\invoice-1005.txt
    Export finished in 6.0 s

The Time in (s) is 6.0 s


## After Modification
OutPut:-
    Starting invoice export...
    Customer files: d:\Diploma\Assignments\Submissions\Assignment-8\saifnasr2-Threads-Assignment\01-InvoiceExport\InvoiceExport\bin\Debug\net9.0\Data
    Invoice output: d:\Diploma\Assignments\Submissions\Assignment-8\saifnasr2-Threads-Assignment\01-InvoiceExport\invoices

    Wrote d:\Diploma\Assignments\Submissions\Assignment-8\saifnasr2-Threads-Assignment\01-InvoiceExport\invoices\invoice-1002.txt
    Wrote d:\Diploma\Assignments\Submissions\Assignment-8\saifnasr2-Threads-Assignment\01-InvoiceExport\invoices\invoice-1004.txt
    Wrote d:\Diploma\Assignments\Submissions\Assignment-8\saifnasr2-Threads-Assignment\01-InvoiceExport\invoices\invoice-1003.txt
    Wrote d:\Diploma\Assignments\Submissions\Assignment-8\saifnasr2-Threads-Assignment\01-InvoiceExport\invoices\invoice-1005.txt
    Wrote d:\Diploma\Assignments\Submissions\Assignment-8\saifnasr2-Threads-Assignment\01-InvoiceExport\invoices\invoice-1001.txt
    Export finished in 1.9 s

The Time in (s) is 1.9 s
