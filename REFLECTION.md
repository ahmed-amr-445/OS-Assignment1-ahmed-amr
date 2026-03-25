# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

Through this assignment, I have been able to understand the workings of Java threads within an operating system simulation. I have been able to understand the basic workings of threads, which are lightweight processes that enable a single process to perform multiple tasks concurrently by sharing the same memory space. In this assignment, I have been able to understand the lifecycle of a thread, where a thread starts from the New state before it progresses to the Runnable state and finally to the Running state after being picked by the scheduler. Using the sleep() method was an eye-opener for me, as it helped me understand the workings of a thread entering the Timed Waiting state. I have also been able to understand the need for the use of the join() method for the main scheduler to wait for the completion of a task before progressing to the next one. Seeing the Round-Robin algorithm work on the threads has helped me understand the fairness and responsiveness offered by modern OSs.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

The hardest part of this assignment was correctly keeping track of the waiting time for Feature 3. It was difficult to manage the timestamps using the System.currentTimeMillis() method as the processes were constantly yielding the CPU and returning to the ready queue after a certain time quantum. I had to make sure that the logic for the waiting time only included the waiting time for the processes and did not include their execution time. Another challenge was making sure the Context Switch Counter was implemented correctly so that it only increased the count when a new process started execution. This required a lot of digging through the loop structure to understand the flow of the simulation.
---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

To address this problem, I used a systematic debugging method by printing logs to the terminal to observe the states of variables such as remainingTime and totalWaitTime. In addition, I studied the documentation of the starter code and the README.md file to understand the relationship between the Process class and the SchedulerSimulation loop. In the waiting time part of the code, I utilized the lastReadyTime field to find the time difference every time a process was retrieved from the queue and scheduled to run. Furthermore, I utilized professional tools such as the built-in Git feature of Visual Studio Code to track my commits on each feature before moving to the next one. This systematic approach helped me detect logic errors and ensured that the context switch counter was being incremented at the right time during the scheduling simulation.
---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

The concepts of multithreading programming are very important for developing real-life applications like Web Browsers, where each tab of the browser can be run on a different thread to ensure that if one website is taking too long to load, it does not freeze the entire window. Another example is Media Players, where one thread can be used for user interface and another thread for decoding and playing a video file in the background. Game Engines also require threads for different tasks like physics, rendering, and sound processing to ensure high frame rates. This assignment has taught me how important the concept of Round Robin Scheduling is for these types of applications, where fairness and avoidance of CPU monopolization by a single task are required. By applying these concepts of multithreading programming, developers can ensure efficiency and predictability of their systems to handle multiple users or tasks at once.

---

## Additional Reflections (Optional)

### What would you like to learn more about?

I am extremely interested in learning more about Thread Safety and the ways to avoid "Race Conditions" that may occur when different threads are trying to access the same data at the same time. Also, I would like to learn more about Advanced Scheduling Algorithms, specifically the "Multilevel Feedback Queues" algorithm, to see the differences between this and the "Round Robin" algorithm that was implemented in the assignment. The way distributed systems deal with concurrency on different servers is something that I find extremely interesting, especially in terms of my future role as a software engineer.

---

### How confident do you feel about multithreading concepts now?

Rating : Intermediate

I am confident in creating threads, handling the life cycle states of threads (New, Runnable, Running, Waiting, Terminated), and implementing basic scheduling algorithms like Round Robin scheduling. Now, I understand how the CPU switches between threads for the sake of fairness and responsiveness in an operating system. However, I think that I still need practice in handling complex synchronization and debugging complex concurrency issues in large software systems.

---

### Feedback on the assignment

This assignment was very useful and well-structured, with a great mix of theoretical concepts related to operating systems and practical Java programming skills. In particular, the use of the visual progress bars and the color coding in the starter code was extremely useful in debugging the scheduling code. Additionally, the use of GitHub was a great experience, which taught me a lot about professional version control best practices.
