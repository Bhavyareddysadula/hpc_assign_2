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

## Output

1. Coarse-Grain Synchronization throughput for different workloads :
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/c2e125a4-a1a7-43cf-b933-2a4d572a2861)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/7becbb74-a765-416f-ba54-38699d3828fd)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/4f748fb4-f47a-4d72-a54a-ad4948f6b886)

2. Fine-Grain Synchronization throuhput for different workloads :
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/737a25dd-f819-4e77-9770-9c445fcb73f0)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/431790ef-0142-4e7a-96aa-0ff1c5900933)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/65b2e4f5-872e-491a-a10d-3bd0360b6d93)

3. Optimistic Synchronization throuhput for different workloads :
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/ab4da44d-179f-4b8b-905b-62559e28bdf1)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/ee081487-0b3e-4ad1-9057-ae48d70ec26c)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/d3b7939a-782a-4e68-98fa-e2a5bca5d302)

4. Lazy Synchronization throuhput for different workloads :
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/45d4fbc3-2b6f-4883-b23b-d28f7830ef04)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/3f8ff2a6-a0ae-4516-ad80-83b55c483a53)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/52991db7-70df-4eaa-8d00-3e5fb2f7489c)

5. Non-Blocking Synchronization throuhput for different workloads :
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/d3ce220f-1a40-465a-a66b-11492ae9110b)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/ed8c4527-b93f-446c-aa4b-3ce02b822f75)
      ![image](https://github.com/Bhavyareddysadula/hpc_assign_2/assets/126856102/28558932-9702-4ea3-8fbf-031e183cbb12)

     
## Results

The program will print the following results to the console:

- Problem size, thread count, workload, execution time, and throughput for each configuration.
