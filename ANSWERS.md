# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process is a program that has its own memory and resources, while a thread is a smaller unit that runs inside a process and shares the same memory. Threads are faster to create and use less resources compared to processes. In this assignment, we used threads because all processes share the same ready queue and scheduler. Using separate processes would make the program more complex and slower. Threads are more suitable because they allow easier communication and better performance in this simulation.


## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
In Round-Robin scheduling, if a process does not finish within its time quantum, it is stopped and moved to the end of the ready queue. It waits there until it gets another turn to run. In my output, P1 ran for 3000ms but it still had 3882ms remaining, so it was stopped and added back to the ready queue. After that, other processes ran before P1 got another chance. This makes sure all processes get a fair share of CPU time.


Example from my output:

P1 completed quantum 3000ms │ Remaining time: 3882ms
P1 yields CPU for context switch
P1 Priority: 3 │ added to ready queue │ Burst time: 6882ms



**Explanation of example:**

This example shows that P1 did not finish in one time quantum, so it was returned to the ready queue. Later, it ran again and finished when its remaining time reached 0. This behavior is important because it prevents one process from using the CPU for too long and keeps the system fair.


---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

In my program, P1 goes through different thread states during execution. First, it is in the New state when the thread is created. Then it becomes Runnable when it is added to the ready queue and waits for its turn. It moves to Running when the scheduler starts it and it begins executing its time quantum. During execution, it goes into a waiting state when Thread.sleep() is used to simulate processing time. Finally, it becomes Terminated when it finishes execution and its remaining time becomes 0.

1. **New**: When P1 thread is created before calling start().

2. **Runnable**: When P1 is added to the ready queue and waiting to run.

3. **Running**: When P1 starts executing its time quantum.

4. **Waiting**: When Thread.sleep() is used during execution.

5. **Terminated**: When P1 finishes execution, like when it ran for 882ms and then ended.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web Browser

**Description**: 
A web browser runs different tasks at the same time, like loading pages, playing videos, and responding to user actions.

**Why Round-Robin works well here**: 
Round-Robin allows each task to run for a short time, which keeps the browser responsive and prevents one task from blocking the others.

### Example 2: Operating System

**Description**: 
An operating system runs multiple programs at the same time, such as apps and background processes.

**Why Round-Robin works well here**: 
Round-Robin gives each program a fair amount of CPU time, so no program takes all the resources and the system stays responsive.

---

## Summary

**Key concepts I understood through these questions:**
1. The difference between threads and processes 
2. How Round-Robin scheduling works 
3. How thread states change during execution 

**Concepts I need to study more:**
1. Thread synchronization
2. Advanced scheduling algorithms
