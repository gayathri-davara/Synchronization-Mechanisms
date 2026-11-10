# Comparison of Synchronization Mechanisms

## Objective
To compare the correctness and execution time of different
synchronization mechanisms in parallel programs.

## Experimental Setup
- Operating System: Ubuntu 22.04.5 LTS
- Compiler: GCC 11.4.0
- Parallel Programming: OpenMP
- Virtual CPUs: 2
- Number of increments: 10,000,000
- Thread configurations: 1, 2, 4, 8

## Experimental Results

| Mechanism | Threads | Final Count | Correctness | Time (s) |
|-----------|--------:|------------:|-------------|---------:|
| None | 1 | 10000000 | Correct | 0.0070 |
| Critical | 1 | 10000000 | Correct | 0.1274 |
| Atomic | 1 | 10000000 | Correct | 0.0767 |
| Lock | 1 | 10000000 | Correct | 0.1298 |
| None | 2 | 5779308 | Incorrect | 0.0128 |
| Critical | 2 | 10000000 | Correct | 0.2697 |
| Atomic | 2 | 10000000 | Correct | 0.1330 |
| Lock | 2 | 10000000 | Correct | 0.3053 |
| None | 4 | 3776804 | Incorrect | 0.0143 |
| Critical | 4 | 10000000 | Correct | 0.3148 |
| Atomic | 4 | 10000000 | Correct | 0.1312 |
| Lock | 4 | 10000000 | Correct | 0.3029 |
| None | 8 | 1255157 | Incorrect | 0.0128 |
| Critical | 8 | 10000000 | Correct | 0.3318 |
| Atomic | 8 | 10000000 | Correct | 0.1280 |
| Lock | 8 | 10000000 | Correct | 0.3417 |

## Observations
1. The unsynchronized implementation produced incorrect
   results with multiple threads due to race conditions.
2. Critical sections ensured correctness by allowing only
   one thread at a time to execute the protected section.
3. Atomic operations ensured correctness and had lower
   execution time than critical sections in this run.
4. OpenMP locks also ensured mutual exclusion but introduced
   synchronization overhead.
5. Increasing the number of threads did not improve the
   execution time in this experiment.

## Conclusion
Synchronization mechanisms prevent race conditions and
ensure correct access to shared data. Atomic operations
performed best among the tested synchronization mechanisms
in this particular benchmark run.

Note: Results are from a single run on a VM with 2 virtual
CPUs. Timings may vary, and configurations with 4 and 8
threads are oversubscribed. Unsynchronized shared increments
in C involve a data race and have undefined behavior.
