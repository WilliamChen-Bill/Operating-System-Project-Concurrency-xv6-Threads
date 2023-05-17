# Exciting OS Project: Introducing Concurrency with xv6 Kernel Threads

Welcome to my cutting-edge Operating System project where I've added real kernel threads to the minimalist educational operating system, xv6. This project gave me the opportunity to delve deep into the intricacies of OS kernel architecture and concurrency, resulting in an exciting and practical learning experience.

## Kernel Threads Magic
For this project, I introduced a new system call to create a kernel thread, `clone()`, and a complementary system call `join()`, to wait for a thread. The magic doesn't stop there. I leveraged these system calls to build a thread library, implementing `thread_create()`, `lock_acquire()`, and `lock_release()` functions. 

## The Project Specifics
The new `clone()` system call creates a kernel thread that shares the calling process's address space. The `join()` system call waits for a child thread to exit, returning the PID of the waited-for child or -1 if none. I also added thoughtful enhancements to existing system calls to ensure seamless integration with the new features.

The thread library I built encapsulates the intricate system calls, offering simple interfaces like `thread_create()` and `thread_join()`. The library also introduces a ticket lock mechanism for better thread synchronization.

The thread library is designed to be part of every program that runs in xv6. Also, special care has been taken to handle the address space growth by a thread in a multi-threaded process.

## Building `clone()` from `fork()`
To implement `clone()`, I took inspiration from the `fork()` system call. The major modification was to enable the new child thread to be in the same address space as the parent, thus eliminating the need to create a copy of the address space.

## Understanding x86 Calling Convention
To succeed in this project, I familiarized myself with the x86 calling convention and the workings of the stack when calling a function. This allowed me to set things up properly on the user stack of the child thread.

This project not only tested my coding skills but also my understanding of core OS concepts. It is a showcase of my ability to work with low-level systems and make significant modifications to them. If you're a recruiter looking for a candidate with solid systems programming skills, you've come to the right place! Feel free to explore the code and don't hesitate to reach out if you have any questions or opportunities.
