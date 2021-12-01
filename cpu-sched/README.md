# Homework (Simulation)

### Q1. 200 * 3
- SJF
  - response time: (0 + 200 + 400)/3 = 200
  - turnaround time: (200 + 400 + 600)/3 = 400
- FIFO
  - same as SJF

### Q2. 100, 200, 300
- SJF
  - response time: (0 + 100 + 300)/3 = 133.33
  - turnaround time: (100 + 300 + 600)/3 = 333.33
- FIFO
  - same as SJF or
  - worse than SJF (depending on the order of arrival)

### Q3. RR time-slice 1
- RR
  - response time: (0 + 1 + 2)/3 = 1
  - turnaround time: (298 + 499 + 600)/3 = 465.67

### Q4. For what types of workloads does SJF deliver the same turnaround time as FIFO?
短い順に並んだworkload

### Q5. For what types of workloads and quantum lengths does SJF deliver the same response times as RR?
job length == quantum(slice) length となるようなworkload

### Q6. response time with SJF
- If job lengths increase then response time increase too.
- Simulations
  - `-l 100,200,300`
    - response time: (0 + 100 + 300)/3 = 133.33
  - `-l 1000,2000,3000`
    - response time: (0 + 1000 + 3000)/3 = 1333.33
  
### Q7. response time with RR
- If quantum lengths increase then response time increase too.
- Simulation
  - `-q 1 -l 100,200,300`
    - response time: (0 + 1 + 2)/3 = 1
  - `-q 10 -l 100,200,300`
    - response time: (0 + 10 + 20)/3 = 10
- Worst-case response time
  - (0 + q + 2q + ... + (N-1)q)/N = (N-1)*q/2