# Critical Section – Experimental Results

## Objective
To ensure mutually exclusive access to a shared counter
using OpenMP critical sections.

## Expected Counter
10000000

## Experimental Results

| Threads | Final Count | Elapsed Time | Correctness |
|---------|------------:|-------------:|-------------|
| 1       | 10000000    | 0.16 s       | Correct     |
| 2       | 10000000    | 0.32 s       | Correct     |

## Observation
Both configurations produced the correct result.

Execution time increased when using two threads
because access to the critical section was serialized.

## Conclusion
Critical sections prevent race conditions by allowing
only one thread at a time to execute the protected code.
However, synchronization overhead can reduce scalability.
