# RESULTS.md

## Setup
Three child processes were created using fork().
Each process was assigned tickets using settickets(int n):

- 10 tickets
- 20 tickets
- 30 tickets

Expected proportional share: 1:2:3.

The process with 30 tickets should receive approximately three times as much CPU time as the process with 10 tickets over a sufficiently long run.

## Workload
Each process executed a CPU-bound infinite loop with no blocking operations, keeping all processes RUNNABLE.

## Observed Behavior
The 30-ticket process ran most often, followed by 20 tickets, then 10 tickets.
Short-term results varied due to randomness, but long runs reflected the expected 1:2:3 ratio.

## Variance and Convergence
Lottery scheduling is probabilistic. Individual selections vary, but over many scheduling decisions the CPU share converges toward the expected proportional distribution.
