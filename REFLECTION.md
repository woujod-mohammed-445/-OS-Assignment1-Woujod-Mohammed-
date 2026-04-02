# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

In this assignment, I learned the fundamentals of multithreading in Java and how threads are created using the Runnable interface. I understood how each process can run independently as a thread and how threads execute concurrently to simulate CPU scheduling. I also learned about thread lifecycle, including starting a thread using start() and waiting for it using join(). One important concept I learned is that a thread cannot be started more than once, which can cause runtime errors. Additionally, I explored how time slicing works using time quantum and how threads share CPU time. What surprised me most was how small mistakes in thread handling can lead to major issues in execution. Overall, this assignment helped me understand how multithreading improves performance and efficiency.

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

The most challenging part of this assignment was debugging the code and fixing thread-related issues. I faced difficulties when the program was not running correctly due to duplicate code and attempting to start the same thread multiple times. Understanding how the scheduler loop works and how processes move in and out of the queue was also confusing at first. Additionally, managing the relationship between threads and process objects using maps required careful attention. The complexity increased when implementing features like waiting time tracking and context switching. These challenges were directly related to understanding how multithreading and scheduling concepts work together. It required both logical thinking and careful code tracing.

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**
To overcome these challenges, I followed a step-by-step debugging approach. First, I carefully read the error messages to understand the problem. Then, I reviewed my code and compared it with the original version to identify differences. I also tested small parts of the code instead of running everything at once. When I faced difficulties, I searched for explanations and examples to better understand the concepts. I focused on fixing one issue at a time, such as removing duplicate code and correcting thread usage. Additionally, I made sure to re-run the program after each fix to confirm the solution. This approach helped me gradually solve all the issues and improve my understanding.
## Question 4: How can you apply multithreading concepts in real-world applications?
**Your Answer:**

Multithreading is widely used in real-world applications to improve performance and responsiveness. For example, web browsers use multiple threads to load web pages, play videos, and handle user input at the same time. In mobile applications, threads allow background tasks like downloading data while the user interacts with the app. Games also use multithreading to handle graphics, physics, and user input simultaneously. In this assignment, the scheduler simulation showed how processes share CPU time efficiently, which is similar to how operating systems manage tasks. Multithreading helps reduce waiting time and improves user experience. Overall, understanding these concepts is important for building efficient and responsive software systems.

## Additional Reflections (Optional)

### What would you like to learn more about?

[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---

### How confident do you feel about multithreading concepts now?

[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment

[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
