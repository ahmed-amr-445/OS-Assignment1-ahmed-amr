# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A process is an independent execution unit that has its own dedicated memory space and system resources assigned by the operating system. In contrast, a thread is a "lightweight" unit of execution that exists within a process and shares the same memory and resources with other threads in that process. We used threads in this assignment because they have much lower creation and context-switching overhead compared to processes, making them more efficient for simulating CPU scheduling. Additionally, threads allow for easier communication and data sharing through the shared process memory, which was necessary for our processMap and shared variables.

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In Round-Robin scheduling, if a process does not finish its execution within the assigned time quantum, it is "preempted" by the scheduler to ensure fairness. The current thread is stopped, and the process is placed at the back of the Ready Queue to wait for its next turn. This prevents any single process from hogging the CPU and ensures that all processes get a chance to run periodically.


Example from my output:

```
⏸ P1 completed quantum 3000ms │ Overall progress: [████░░░░░░] 40%
     Remaining time: 4500ms
  ↻ P1 yields CPU for context switch
  ➕ P1 added to ready queue │ Burst time: 7500ms

```

**Explanation of example:**

In this snippet, P1 ran for the full time quantum (3000ms) but still had 4500ms remaining. Because it wasn't finished, the program printed a "yields CPU" message and used the addProcessToQueue method to put P1 back at the end of the queue.
---


## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

Throughout the simulation, a process like P1 transitions through various lifecycle states as managed by the Java Virtual Machine (JVM)

1. **New**: P1 is in the New state immediately after the new Thread(process) statement is executed but before start() is called

2. **Runnable**: P1 enters the Runnable state after currentThread.start() is called, meaning it is ready to execute and waiting for the JVM thread scheduler to give it CPU time

3. **Running**: [P1 is in the Running state when the code inside its run() method is actually being executed by the processor]

4. **Waiting**: P1 enters a Timed Waiting state during the Thread.sleep(stepTime) calls which simulate the time taken for execution

5. **Terminated**: P1 reaches the Terminated state once the run() method finishes execution because the remainingTime has reached zero.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Web Server Handling Requests]

**Description**: 
A web server (like Apache or Nginx) handling multiple simultaneous user requests to view different pages on a website

**Why Round-Robin works well here**: 
It provides excellent responsiveness and fairness. By giving each request a small time slice, the server ensures that no single large file download blocks other users from loading simple text pages, keeping the system interactive for everyone.

### Example 2: [Multitasking in Modern Operating Systems]

**Description**: 
A desktop OS (like macOS or Windows) running multiple applications at once, such as a web browser, a music player, and VS Code.

**Why Round-Robin works well here**: 
It allows the user to feel like all programs are running "simultaneously". Because the time quantum is very small, the CPU switches between these apps so fast that the music keeps playing smoothly while you type code, providing a seamless multitasking experience.

---

## Summary

**Key concepts I understood through these questions:**
1. The efficiency of using Threads for concurrent tasks over heavy Processes.
2. How Round-Robin ensures fairness by using time quantums and a Ready Queue.
3. The importance of Thread synchronization and lifecycle states in Java.

**Concepts I need to study more:**
1. Thread Safety and Synchronization
2. Advanced Scheduling Algorithms
