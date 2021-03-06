
**CSCI 3453 -- Operating Systems Concepts**

Lab Assignment 2

Due Date  :  Oct. 30, 2017

-----------------

# 1. Goal of this assignment

> 
The primary goal of this lab assignment is to understand various CPU scheduling algorithms and gain some experience building 
a simulator for CPU scheduling algorithm to evaluate their performances.
>

-----------------

# 2. Lab assignment description

> 
Write a C/C++ program to simulate a CPU scheduler which selects a processor from a ready queue and executes the process by a 
given scheduling algorithm, display its actives and evaluate its performance based on collected some measurements such 
as average turn-around time, average waiting time, average response time. When a process is scheduled, the simulator will 
simply print what the process is running at what time, collecting some measurement data and producing Gantt Chart-like outputs. 
>

-----------------

# 3. Specification 

> 
- Implement FCFS ( First Come First Serve)
- SRTF ( Shortest Remaining Task First)
- RR (Round Robin), PP(Preemptive Priority) scheduling algorithms
- Must create a PCB Structure 
- Cannot use any STD library for building queue and managing the ready queue. 
For example, you cannot use STD/STL for queue or linked list, 

DO NOT USE any built-in queue library or class ( do not use stl library in C++ or C). You have to implement your own queue management functions (or method).

>

-----------------

# Assumptions 
There is only one CPU
- All processes perform only CPU operations
- 0 Highest Priority and 100 lowest priority 
- The new arrival process is directly stored at the ready queue.
- We use only ready queue for this simulation.
- We take into consideration of context switching cost. 
- We assume the context switching cost is 0.5 milliseconds when a context switching is occurred.
- Context switch is performed only when a current process is moved to the ready queue.  
- The time of unit is milliseconds.
- We use FCFS policy for breaking the tie. (For SRFT, Round-Robin, and PP case)
 
-----------------

# Measurements 
You should collect the following information of each process:

- Time of completion
- Waiting time
- Turnaround time
- Response time
- No. of Context occurred You should calculate the following information using collected measurements:
- Average CPU burst time
- Average waiting time
- Average turn around time
- Average response time
- Total number of Context Switching performed Please refer Chapter 6 in textbook and lecture notes for all detail information about the measurements: waiting time, turn around time, response time, average waiting time, average turn around time, and average response time.

-----------------

# Simulator Input

> There are three inputs will be given as arguments when the simulator begins.
>

**1. Process arrival information** (expect total number of arrival processes are up to 100)
The process information will be read from a text input file. The information for each process will include the following fields: 
 -  pid: a unique numeric process ID.
 -  arrivaltime: the time when the task arrives in the unit of milliseconds
 -  CPU bursttime: the CPU time requested by a process              
 -  Priority : priority of arrival process 

**2. Type of scheduling algorithm**

You will be implementing four scheduling algorithms, and you will select one algorithm when you start the simulator as the 3rd argument. You will enter an integer value from one of the followings:
- FCFS:  unixprompt> myscheduler test-input-file-name  output-file-name 0  
- SRTF:  unixprompt> myscheduler test-input-file-name  output-file-name  1  
- RR:    unixprompt> myscheduler test-input-file-name  output-file-name 2 quantum size
- PP:    unixprompt> myscheduler test-input-file-name  output-file-name 3

**3. Time Quantum size**

You will define the time quantum when the simulator begins as the first argument. The timequantum is essential for the RR scheduling and the timequantum value is an integer value and should be greater than 0.  Thus, your program should be able to take the time quantum value as the first input value. So, your program will be executed as follows:

> unixprompt> myscheduler test-input-file-name  output-file-name 2 4

>
