# Atomic Operation – Experimental Results

## Objective
To perform thread-safe updates on a shared counter
using OpenMP atomic operations.

## Expected Counter
10000000

## Experimental Results

| Threads | Final Count | Elapsed Time | Correctness |
|---------|------------:|-------------:|-------------|
| 1       | 10000000    | 0.10 s       | Correct     |
| 2       | 10000000    | 0.10 s       | Correct     |

## Observation
Both executions produced the expected counter value.

Atomic operations provided better measured execution
times than critical sections in our initial runs.

## Conclusion
Atomic operations provide indivisible updates for
supported operations and reduce synchronization
overhead for simple shared-variable modifications.
