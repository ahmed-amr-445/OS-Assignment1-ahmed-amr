# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 23, 2026, 7:57 AM]
**What I did**: Initial project setup and student ID configuration. 

**Details**: 
- Created GitHub account with my university email.
- Forked the repository and cloned it to my MacBook.
- Updated the studentID variable to 445052835 to seed the random generator.
- Ran the initial code to understand the Round-Robin logic.

**Challenges**: Making sure the Java environment was ready on my VS Code.

**Solution**: Verified the JDK installation and tested a simple print statement.

**Time spent**: 35 minutes

---

### Entry 2 - [March 23, 2026, 8:57 AM]
**What I did**: Implemented Feature 1: Process Priority.

**Details**: 
- Added the priority field to the Process class.
- Modified the constructor to accept priority. 
- Updated the main loop to generate random values (1-5).

**Challenges**: Updating the constructor without breaking the existing object creation.

**Solution**: Carefully refactored the Process instantiation in the main method.

**Time spent**: 1 hour

---

### Entry 3 - [March 23, 2026, 5:49 PM]
**What I did**: Implemented Feature 2: Context Switch Counter.

**Details**: 
- Added a static contextSwitches variable in the SchedulerSimulation class.
- Incremented the counter inside the while loop right before each thread starts.
- Displayed the total count (18 in my test run) at the end of the simulation.

**Challenges**: Locating the exact point where a "switch" occurs in the loop.

**Solution**: Placed the increment logic before currentThread.start() to count every time the CPU picks a new thread.

**Time spent**: 1 hour

---

### Entry 4 - [March 23, 2026, 7:41 PM]
**What I did**: Implemented Feature 3: Waiting Time Tracking.

**Details**: 
- Added creationTime, totalWaitTime, and lastReadyTime fields to the Process class.
- Updated the logic in run() and addProcessToQueue to calculate time spent in the queue.
- Created a final summary table to display the results.

**Challenges**: Managing the time timestamps correctly for processes that yield and re-enter the queue.

**Solution**: Used System.currentTimeMillis() to track when a process enters and leaves the "Ready" state.

**Time spent**: 1.5 hours  

---

### Entry 5 - [March 24, 2026, 7:48 AM]
**What I did**: Final Documentation and Code Review.

**Details**: 
- Completed all the technical questions in ANSWERS.md.
- Provided specific examples from my terminal output for the Ready Queue behavior.
- Conducted a final code review to ensure all three features (Priority, Counter, and Waiting Time) work together seamlessly.

**Challenges**: Formatting the terminal output snippets inside the Markdown file to ensure they are readable on GitHub.

**Solution**: Used triple backticks (```) to create code blocks, which preserves the ANSI-like structure and makes the output snippets clear and professional on the repository page.

**Time spent**: 1.5 hour

---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [5 hours and 35 minutes.]

**Most challenging part**: Implementing Feature 3 (Waiting Time Tracking) was the most difficult because it required careful management of timestamps using System.currentTimeMillis() as processes moved between the Running and Ready states multiple times.

**Most interesting learning**: Gaining a hands-on understanding of the Thread Lifecycle (New, Runnable, Running, Waiting, Terminated) and seeing how a Round-Robin scheduler manages these states to ensure CPU fairness.

**What I would do differently next time**: I would implement a dynamic input system that allows users to add new processes while the scheduler is already running, making the simulation feel more like a real-time operating system.
