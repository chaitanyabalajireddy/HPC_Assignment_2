# HPC_Assignment_2 
Created a concurrent double-linked list (sorted list) using the following synchronization techniques:

- Coarse-grain Synchronization
- Fine-grain Synchronization
- Optimistic Synchronization
- Lazy Synchronization
- Non-blocking Synchronization

Verified the performance of the concurrent data structure for different problem sizes (2 × 1000, 2 × 10000, and 2 × 100000) by varying the number of threads (1, 2, 4, 6, 8, 10, 12, 14, and 16) and workloads (0C-0I-50D, 50C-25I-25D, and 100C-0I-0D).

### Coarse-grain Synchronization
Coarse-grained synchronization involves locking the entire data structure (in this case, the entire doubly linked list) to protect it from concurrent access. When one thread acquires the lock, it has exclusive access to the entire list, preventing other threads from accessing it until the lock is released.
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/187cb598-4f62-4ed6-b154-ef576578a328)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/36fe339c-aafc-4610-b9f6-53126521b54f)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/c513b0ce-e485-4161-80a7-2c1219b7381b)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/3b7b48e1-6c45-4f61-a906-0f3c8dbbce09)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/0517480d-5de5-4e85-a89e-f06f56ab5820)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/46d05032-aaa0-4dea-8c35-98334ac01c10)

### Fine-grained synchronization
Fine-grained synchronization divides the doubly linked list into smaller, independently locked sections. Each section (e.g., a node or a group of nodes) has its lock. Threads can operate concurrently on different sections, reducing contention.
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/80d74f91-76bd-43e3-b263-54803ad832dd)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/06611d2b-1d20-41db-bfca-61c4214261be)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/62f3bc73-001a-4687-8214-f7fbdd1df5ee)

### Optimistic Synchronization
Optimistic synchronization assumes that conflicts between threads are rare. Instead of locking data structures, each thread reads and makes modifications locally. Before applying changes, the thread validates that no other thread has modified the same data. If conflicts occur, the thread retries the operation.
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/e5eae4cf-c0fc-4e3a-b9ca-3462c363e911)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/afb4dc79-7e91-470f-8ddb-741dbb35b609)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/882743ef-6a39-4c09-bb78-0a652226c9d4)

### Lazy Synchronization
 Lazy synchronization aims to delay synchronization until absolutely necessary. Threads perform operations without initially acquiring locks. Only during critical sections or when conflicts are detected are locks acquired to ensure data consistency.
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/7a9050aa-b71b-4785-aea5-cce210ee930a)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/642622da-8eae-44dd-877f-7c298a9c2666)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/0d06287f-e693-4bc1-ae30-c6dcc546e4e4)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/6620892a-54d6-459c-804c-be26cfa4eec0)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/c89df827-7ee6-4366-b4a1-d76e160ea830)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/d4a135d6-b536-4dc0-8b2f-403ff2e3ec39)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/6df65fc2-202f-40f6-aea9-d2d13a7b1154)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/11c019a2-e52b-4db3-a472-eb91017465da)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/e5efa610-aee5-489d-b501-621bfe3fd661)

### Non-blocking Synchronization
Non-blocking synchronization techniques aim to eliminate the use of locks entirely. Instead, atomic operations, such as compare-and-swap (CAS), are used to modify data structures in a thread-safe manner. If a CAS operation fails due to a concurrent modification, the thread retries the operation.
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/08996c5d-3ef2-45f1-a509-ee3f405eda76)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/2f0b2621-fc13-4c8f-bc64-0304f8b94e98)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/9aa9da78-8d5e-4e56-b23e-6010eb2a9d94)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/364d836e-08a7-48c0-970b-714e7014ded1)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/eb211099-425e-487f-b0d0-3145bbdba293)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/7bf5ec37-2c75-4f69-8b80-66504fc88556)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/59db95b0-db0d-462b-912c-70b11b174b76)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/1ec38168-a270-4c13-955a-5cff8ebaefbe)
![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_2/assets/91625648/208c8571-ae50-4fa4-85e8-ee633233a1d0)

NOTE: In some techniques for a problem siza 3 individual graphs are plotted due to different range of throughput for each workload.
