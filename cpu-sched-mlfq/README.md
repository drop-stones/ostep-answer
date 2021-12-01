# Homework (Simulation)

### Q1.  MLFQ execution trace
`python3 mlfq.py -j 2 -n 2 -m 10 -M 0 -c`

Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] JOB BEGINS by JOB 1
[ time 0 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 7 (of 8) ]
[ time 1 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 6 (of 8) ]
[ time 2 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 5 (of 8) ]
[ time 3 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 4 (of 8) ]
[ time 4 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 3 (of 8) ]
[ time 5 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 2 (of 8) ]
[ time 6 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 1 (of 8) ]
[ time 7 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 0 (of 8) ]
[ time 8 ] FINISHED JOB 0
[ time 8 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 3 (of 4) ]
[ time 9 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 2 (of 4) ]
[ time 10 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 1 (of 4) ]
[ time 11 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 0 (of 4) ]
[ time 12 ] FINISHED JOB 1

Final statistics:
  Job  0: startTime   0 - response   0 - turnaround   8
  Job  1: startTime   0 - response   8 - turnaround  12

  Avg  1: startTime n/a - response 4.00 - turnaround 10.00

### Q2. Examples in this chapter

Figure 8.2: `python3 mlfq.py -j 1 -n 3 -q 10 -l 0,200,0 -c`
Figure 8.3: `python3 mlfq.py -j 2 -n 3 -q 10 -l 0,200,0:100,20,0 -c`
Figure 8.4: `python3 mlfq.py -j 2 -n 3 -q 10 -l 0,200,0:50,25,1 -c`
Figure 8.5: `python3 mlfq.py -j 3 -n 3 -q 10 -l 0,200,0:100,50,5:105,50,5 -S -c`
            `python3 mlfq.py -j 3 -n 3 -q 10 -l 0,200,0:100,50,5:105,50,5 -S -B 50 -c`
Figure 8.6:
Figure 8.7: `python3 mlfq.py -j 2 -n 3 -Q 10,20,40 -l 0,70,0:10,70,0 -c`

### Q3. Like Round-Robin

Please add `-n 1`.  
`python3 mlfq.py -j 3 -n 1 -l 0,10,0:0,20,0:0,30,0 -c`

### Q.4 Game the scheduler and Obtain 99% of the CPU

Job1: 99ms -> IO (1ms)  
Job0:  1ms  
Job1: 99ms -> IO (1ms)  
...
`python3 mlfq.py -j 2 -n 3 -q 100 -l 0,500,0:0,500,99 -S -i 1 -c`

### Q.5 Long-running job can get at least 5% of the CPU

Boost at every 200ms guarantee that job can get at least 5% because job can do 10ms per 200ms.
Please add `-B 200`.
`python mlfq.py -j 2 -n 3 -q 10 -l 0,100,0:0,100,9 -S -i 1 -B 200 -c`

### Q.6 Push head/back to a queue when finished IO

- push back: `python3 mlfq.py -j 2 -n 3 -q 20 -l 0,20,2:0,20,2 -i 1 -c`
- push head: `python3 mlfq.py -j 2 -n 3 -q 20 -l 0,20,2:0,20,2 -i 1 -I -c`