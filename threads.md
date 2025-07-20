1. **Thrashing** is the situation when the CPU spends more time in context switching rather than executing the threads.

2. **Starvation** is a situation when a long thread is executing and other threads are waiting for a long time to get executed.

3. `thread.interrupt();`  
   To interrupt a thread that is running, we can use one of the following approaches:
   - a. A process that throws the `InterruptedException` (e.g., `Thread.sleep()`).
   - b. `Thread.currentThread().isInterrupted()` and then return.

4. `thread.setDaemon(true)` will stop the thread as soon as the parent thread completes the process in which context the current daemon thread is running.

5. `thread.join(timeToWait);`

6. **Reduce latency and increase throughput**

7. **Critical Section**: It is the section which needs to be executed by at most one thread at any point in time.

8. The above locking mechanism can be achieved using the `synchronized` keyword. Two ways of doing this:
   - a. **Synchronized method**: This ensures that any synchronized methods in the class will not be accessed concurrently. One lock per object. This is called a **Monitor**.
   - b. **Synchronized block**: Used to secure a critical block or section without locking the entire object.

9. All assignments to and reads from **primitive datatypes** are atomic **except** for `long` and `double`.

10. **Reference assignments** are atomic.

11. `java.util.concurrent.atomic` is the package that has classes to perform atomic operations.

12. The **`volatile`** keyword is used to synchronize the setter and getter of the `long` and `double` datatypes.

13. **Race Condition**: Occurs when two or more threads try to access a shared resource while one of them is modifying the value in a non-atomic way.

14. **Data Race**: A condition where instructions are reordered and executed randomly, leading to incorrect behavior when accessing shared resources. The `volatile` keyword helps prevent this.

15. By using the `volatile` keyword, the instructions **before** are executed first and the instructions **after** are executed later — hence order is maintained.

16. **Conditions for Deadlock**:
   - a. Mutual exclusion
   - b. Hold and wait
   - c. Non-preemptive allocation
   - d. Circular wait

   If all four conditions are met, then deadlock is bound to happen. Avoiding even one can prevent deadlock.

17. Locking Strategies:
   - a. **Coarse-grained locking**
   - b. **Fine-grained locking**

18. **Advanced Locking**:
   - a. `ReentrantLock`
     ```java
     ReentrantLock lockObject = new ReentrantLock();
     lockObject.lock();
     try {
         use(resource);
     } finally {
         lockObject.unlock();
     }

     if (lockObject.tryLock()) {
         try {
             use(resource);
         } finally {
             lockObject.unlock();
         }
     }

     lockObject.lockInterruptibly();
     ```
   - b. `ReentrantReadWriteLock`
     ```java
     ReentrantReadWriteLock lockObject = new ReentrantReadWriteLock();
     lockObject.readLock();
     lockObject.writeLock();
     ```

19. **Semaphores**: A type of lock, but not used the same way as others. It controls how many threads can access the critical section at once. Commonly used in **Producer-Consumer** problems.

20. **Interprocess Communication** can be achieved via:
   - a. `thread.join();`
   - b. `semaphore.acquire()` and `semaphore.release();`
   - c. `thread.interrupt();`

21. **Reentrant Conditions**:
   ```java
   ReentrantLock re = new ReentrantLock();
   Condition condition = re.newCondition();
   condition.await();    // Suspends the thread
   condition.signal();   // Signals waiting threads
