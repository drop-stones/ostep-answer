# Homework(Simulation)

1. CPU Busy 100.0%
2. 4 + 7(= issue-io + wait_5 + io_done) = 11
3. 1(issue-io) + 4(process) + 1(wait) + 1(io_done) = 7
4. 7(= issue-io + wait-5 + io_done) + 7 = 11 (same as Q2)
5. 1 + 4 + 1 + 1 = 7 (same as Q3)
6. System resources are not effectively utilized because cpu doesn't work during io waits.
7. System resources are effectively utilized. `IO_RUN_IMMEDIATE` work well because process with lots of IO will wait for IO repeatedly.
8. Overall, `IO_RUN_IMMEDIATE` is better because of IO intensive process. `SWITCH_ON_IO` is better because of IO wait.

Answer for Q.8
- `-s 1`
  - `IO_RUN_LATER` or `IO_RUN_IMMEDIATE`: no effect
  - `SWITCH_ON_IO` or `SWITCH_ON_END`: faster when `SWITCH_ON_IO`
- `-s 2`
  - `IO_RUN_LATER` or `IO_RUN_IMMEDIATE`: no effect
  - `SWITCH_ON_IO` or `SWITCH_ON_END`: faster when `SWITCH_ON_IO`
- `-s 3`
  - `IO_RUN_LATER` or `IO_RUN_IMMEDIATE`: faster when `IO_RUN_IMMEDIATE`
  - `SWITCH_ON_IO` or `SWITCH_ON_END`: faster when `SWITCH_ON_IO`

