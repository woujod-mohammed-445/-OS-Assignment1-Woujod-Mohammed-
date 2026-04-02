# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A process is an independent program in execution with its own memory space, while a thread is a smaller unit of execution within a process that shares the same memory. In this assignment, we used threads instead of processes because threads are lighter, faster to create, and allow easier communication between tasks.

One key difference is memory sharing. Threads share the same memory space, which allows them to access shared data structures like the processMap and processQueue in SchedulerSimulation.java. In contrast, processes have separate memory, making communication slower and more complex.

Another difference is creation overhead. Creating a thread using new Thread(process) is much faster than creating a new process, which requires more system resources.

We used threads specifically because the simulation requires frequent switching between tasks (context switching), and threads handle this efficiently. For example, in the code:

Thread thread = new Thread(process);

Each process is executed as a thread, allowing smooth scheduling and faster execution.

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
In Round-Robin scheduling, if a process does not finish within its time quantum, it is paused and placed back into the ready queue to wait for its next turn.

For example, from the program output:

▶ P1 executing quantum [3000ms]
⏸ P1 completed quantum 3000ms │ Remaining time: 2000ms
↻ P1 yields CPU for context switch
➕ P1 added to ready queue

This shows that process P1 did not finish, so it was re-queued for another round.

This behavior is important for fairness because it ensures that no single process can monopolize the CPU. Each process gets a fair share of execution time. By re-queueing unfinished processes, the scheduler guarantees that all processes will eventually be executed.

In the code, this behavior is implemented here:

if (!process.isFinished()) {
    addProcessToQueue(process, processQueue, processMap);
}

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: P1 is in the New state when the thread is created using:
Thread thread = new Thread(process);
At this point, the thread exists but has not started execution yet.

2. **Runnable**: P1 moves to the Runnable state when:
thread.start();
is called. The thread is now ready to run and waiting for CPU scheduling

3. **Running**: P1 is in the Running state when it actually starts executing the run() method.
This happens when the scheduler gives it CPU time to execute its time quantum

4. **Waiting**: 
P1 enters the Waiting state when Thread.sleep(stepTime); is executed inside the loop to simulate execution time.
Also, the main thread goes into waiting when it calls thread.join(); to wait for P1 to finish its quantum.

5. **Terminated**: 
P1 reaches the Terminated state when it finishes execution (i.e., remainingTime <= 0).
At this point, the thread has completed its task and will not run again.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**
Example 1: Web Server

Description:
A web server handles multiple client requests at the same time. Each request can be processed by a separate thread.

Why Round-Robin works well here:
Round-Robin ensures that every client request gets a fair share of CPU time.
It prevents one request from blocking others, improving responsiveness.
This makes the system more efficient and provides better user experience when many users access the server simultaneously.

Example 2: Operating System Task Scheduling

Description:
An operating system runs multiple applications at the same time, such as browsers, music players, and background processes.

Why Round-Robin works well here:
Round-Robin scheduling ensures fairness by giving each process a fixed time quantum.
This prevents any single application from taking all CPU resources.
It also improves system responsiveness, making sure all applications appear to run smoothly from the user's perspective.
## Summary

**Key concepts I understood through these questions:**
1. The difference between threads and processes and how threads share memory and reduce overhead.
2. How Round-Robin scheduling works, especially the concept of time quantum and re-queuing processes for fairness.
3. The thread lifecycle (New, Runnable, Running, Waiting, Terminated) and how it applies to real execution using methods like start(), sleep(), and join().

**Concepts I need to study more:**
1. Advanced thread synchronization concepts such as race conditions and how to avoid them.
2. More complex CPU scheduling algorithms and how they compare to Round-Robin in different scenarios.
