# Homework (Simulation)

### Q.1 simulation
- `python3 lottery.py -j 3 -s 1 -c`
- `python3 lottery.py -j 3 -s 2 -c`
- `python3 lottery.py -j 3 -s 3 -c`

### Q.2 ticket imbalance

`python3 lottery.py -j 2 -l 10:1,10:100 -s ?`

Ticket imbalance in lottery scheduling 

### Q.3 How unfair is the scheduler?

- `python3 lottery.py -j 2 -l 100:100,100:100 -c`
  - Job0: 192, Job1: 200
- `python3 lottery.py -j 2 -l 100:100,100:100 -c -s 1`
  - Job0: 200, Job1: 196 
- `python3 lottery.py -j 2 -l 100:100,100:100 -c -s 2`
  - Job0: 200, Job1: 190 
- `python3 lottery.py -j 2 -l 100:100,100:100 -c -s 3`
  - Job0: 196, Job1: 190 

U = (192 + 196 + 190 + 196) / (200 * 4) = 0.9675

### Q.4 Increase quantum size

`python3 lottery.py -j 2 -l 100:100,100:100 -q 10 -c`: Job0: 200, Job1: 150

When we increase quantum size, we also increase the unfairness.

### Q.5
TODO