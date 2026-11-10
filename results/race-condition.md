# Race Condition – Experimental Results

## Objective
To observe the effect of multiple threads
updating a shared counter without synchronization.

## Expected Counter
10000000

## Experimental Results

| Threads | Actual Counter | Correctness |
|---------|---------------:|-------------|
| 1       | 10000000       | Correct     |
| 2       | 5811036        | Incorrect   |

## Observation
With one thread, the expected result was obtained.

With two threads, multiple threads accessed and
updated the shared counter concurrently.

Some updates were lost due to a race condition.

## Conclusion
Unsynchronized access to shared data can produce
incorrect and unpredictable results.
