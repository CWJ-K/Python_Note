<!-- omit in toc -->
# Table of Contents
- [Introduction](#introduction)
- [Fundamental Concepts](#fundamental-concepts)
  - [Networks](#networks)
- [What is Parallel Computing?](#what-is-parallel-computing)
  - [Parallel Applications](#parallel-applications)
    - [Multithread Programming](#multithread-programming)
    - [Multiprocessing](#multiprocessing)
  - [Advantages of Parallel Computing](#advantages-of-parallel-computing)
  - [Disadvantages of Parallel Computing](#disadvantages-of-parallel-computing)
- [What is Distributed Computing?](#what-is-distributed-computing)
  - [Advantages of Distributed Computing](#advantages-of-distributed-computing)
  - [The Biggest Challenge of Distributed Computing](#the-biggest-challenge-of-distributed-computing)
- [Differences Between Parallel and Distributed Computing](#differences-between-parallel-and-distributed-computing)
- [Amdahl's law](#amdahls-law)
- [Structure of this directory](#structure-of-this-directory)
<br />


# Introduction
This README.md introduces the fundamental concepts of distributed computing.


This directory takes references from [Distributed Computing with Python: Harness the power of multiple computers using Python through this fast-paced informative guide](https://www.amazon.com/Distributed-Computing-Python-Francesco-Pierfederici/dp/1785889699)


<br />

# Fundamental Concepts
## Networks
* Local Area Network (LAN): networks machines are located in the same office/building
* Wide Area Networking (WAN): networks machines are located across different buildings and cities.
* Graphics Processing Unit (GPU)

<br />

# What is Parallel Computing?
* the simultaneous use of more than one processor on the same machine.

<br />

## Parallel Applications
### Multithread Programming
* **Threads** are the typical tools used in parallel techniques, however, they have some limitations
* an example of shared-memory architecture
  
<br />

### Multiprocessing
* an example of distributed memory architecture

<br />

## Advantages of Parallel Computing
1. Improve Performance: break up a task into small parts and execute the small parts in the same amount of time, which enables to speed up the execution time of the task
2. Provide responsive interfaces
    * updating the conditions of the thread requires another task
    * Parallel computing has a main thread and worker thread. A main thread can distribute heavy tasks to the worker thread and has enough resources to update its condition to the GUI.
3. in shared-memory systems, the execution time of tasks is faster than using networks to communicate
4. in shared-memory systems, writing codes are simpler

<br />

## Disadvantages of Parallel Computing
1. in shared-memory systems, multiple treads at the same time may lead to any changes in an unexpected order

<br />

# What is Distributed Computing?
* the simultaneous use of more than one machine.

<br />

## Advantages of Distributed Computing
1. enable to solve problems that no individual can handle
2. enable to solve problems that are not solved in a reasonable amount of time
3. distributed memory systems are salable and cheap to assemble
4. access memory in isolation without racing conditions

<br />

## The Biggest Challenge of Distributed Computing
* Not about CPU, but **data** - how to share data across different machines? 

<br />

# Differences Between Parallel and Distributed Computing
1. in principle, whether tasks can access the same memory space
2. Parallel Computing
3. in distributed memory systems, sharing data across machines is a challenge
4. not all algorithms easily map to the architecture 


```mermaid
graph TD;
    CPU_1 <--> Memory;
    CPU_2 <--> Memory;
    CPU_3 <--> Memory;
    CPU_4 <--> Memory;
```
* Distributed Computing
    * across the same network
```mermaid
flowchart TB
    subgraph Machine 1
    CPU_1 <--> Memory_1
    end

    subgraph Machine 2 

    CPU_2 <--> Memory_2;
    end

    subgraph Machine 3
    CPU_3 <--> Memory_3;
    end

    subgraph Machine 4
    CPU_4 <--> Memory_4;
    end
 
```
* in reality, computers are a hybrid of parallel and distributed computing

<br />

# Amdahl's law
* code can not be faster than the speed of combined sequential parts of a single process
> a single process = sequential part + parallelized part
  * because the sequential part is required: copy data or code across different processors

* even if tasks are fully parallelized, there is diminishing returns in the speed of execution time as the number of processors increases
* Gustafson's law

<br />

# Structure of this directory
* Celery