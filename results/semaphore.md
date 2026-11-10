# Semaphore Synchronization – Experimental Results

## Objective
To implement mutual exclusion using POSIX semaphores
and POSIX threads.

## Expected Counter
200000

## Experimental Results

| Execution | Final Counter | Correctness |
|-----------|--------------:|-------------|
| 1         | 200000        | Correct |
| 2         | 200000        | Correct |
| 3         | 200000        | Correct |
| 4         | 200000        | Correct |
| 5         | 200000        | Correct |
| 6         | 200000        | Correct |

## Observation
All six executions produced the expected counter value.

## Conclusion
The binary semaphore ensures mutual exclusion by
controlling access to the shared counter using
sem_wait() and sem_post().
