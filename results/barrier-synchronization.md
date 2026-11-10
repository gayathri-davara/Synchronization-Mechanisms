# Barrier Synchronization – Experimental Results

## Objective
To synchronize multiple threads using OpenMP barriers.

## Experimental Configurations

| Threads | Before Messages | After Messages | Status |
|---------|----------------:|---------------:|--------|
| 2       | 2               | 2              | Passed |
| 4       | 4               | 4              | Passed |
| 8       | 8               | 8              | Passed |

## Observation

All threads executed the statements before the barrier
before any thread executed the statements after it.

The order of thread execution varied between runs.

## Conclusion

The OpenMP barrier synchronizes parallel execution
by making threads wait until all participating threads
have reached the synchronization point.
