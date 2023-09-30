# hpc_assign_2

# Concurrent Double-Linked List

## Introduction

This Java program showcases a concurrent double-linked list data structure and assesses its performance by employing different synchronization methods. The objective is to gauge the efficiency of this concurrent data structure across a range of scenarios, including different problem sizes, thread counts, and workloads.

### Synchronization Techniques

1. Coarse-Grain Synchronization: In this approach, the entire list is locked when any operation is performed. This means only one thread can access the list at a time, ensuring exclusive access during operations.

2. Fine-Grain Synchronization: Instead of locking the entire list, locks are applied at a more precise level, often at the node or section level. This allows multiple threads to work on different parts of the list concurrently without blocking each other.

3. Optimistic Synchronization: This technique combines optimistic reading with CAS (Compare-and-Swap) operations. It attempts to perform operations without locking and only resorts to locking if conflicts arise, minimizing the use of locks.

4. Lazy Synchronization: Operations are initially executed without any form of synchronization. Locking is introduced only when conflicts or potential issues are detected, which can help reduce contention for locks.

5. Non-Blocking Synchronization: This method relies on atomic operations and CAS to perform operations without traditional locking mechanisms. It ensures that multiple threads can access and modify the data structure without blocking each other, promoting non-blocking concurrent access.

## Workloads

Three types of workloads:

1. 0C-0I-50D (Workload 1)
   - 0% Inserts, 0% Reads, 50% Deletes
   - Simulates a workload with mostly delete operations.

2. *50C-25I-25D (Workload 2)*
   - 50% Inserts, 25% Reads, 25% Deletes
   - A mixed workload with a balanced combination of operations.

3. *100C-0I-0D (Workload 3)*
   - 100% Reads, 0% Inserts, 0% Deletes
   - Simulates a workload with only read operations.

## Execution 

1. Compile the Java code:
   bash
    javac ConcurrentLinkedListTest.java
   
2. Run the tests using the following command:

   bash
    java ConcurrentLinkedListTest <problemSize> <numThreads> <workload>
   
   Example : 
   bash
    java ConcurrentLinkedListTest 2000 2 "50C-25I-25D"
   
3. The program will execute tests for various problem sizes (2 x 10^3, 2 x 10^4, 2 x 10^5), thread counts (1, 2, 4, 6, 8, 10, 12, 14, 16), and workloads (0C-0I-50D, 50C-25I-25D, 100C-0I-0D).


## Results

The program will print the following results to the console:

- Problem size, thread count, workload, execution time, and throughput for each configuration.
