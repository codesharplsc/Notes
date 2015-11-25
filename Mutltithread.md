##Multithread-programming under POSIX principle

>Having classes about Operation System, a summary about these chapters.

To perform a better goal of concurrency and parallel, we will mostly choose to implement this kind of staff in multithread condition. For computers with only one processor, this is not genuine simultaneously.For computers that has different processors(which is common nowadays), the program can run in parallel. 

Under Unix system, creating a process is not difficult. But we must first be aware it is the thread that is the  running unit. A operation system has different processes, each processes may have not only one thread. For most cases, the code we write has only one main thread if no `-lpthread` option is specified. Code executes in a pre-defined order, however in multithread situation, it is not easy to tell which thread is executing, this may bring conflicts when visiting shared variables and other synchronization problem.

###Thread system call

To begin with, we have the API to create thread, calling

	pthread_create(pthread_t *thread,
					const pthread_attr_t *attr, 
					void *(*start_routine)(void*),
					void *arg)
`thread` will be used to return the value of the threadID, `attr` is set to maintain the detailed information of the thread control, like the security attribute, stack size and so on, `start_routine` is for the thread's routine, and arg is the argument passing to the thread.This somehow determines the thread routine should look like this:

	void * FunctionName (void * arg)
	
Threads don't have a parent/child relationship between each other,but the main thread is kind of unusual because when it call `exit()`, all of the other threads that shares the same process is also going to exit at the same time. So you will probably need some kind of mechanism to avoid this situation happening. Here comes the use of
 
	int pthread_join(thread_t thread,
					(void **)ret_value);
	
	int pthread_exit(int);
	
This first function calls perform a way for one thread to wait for another thread to execute and finish, then it will continue to execute. During the waiting time, the thread is blocked. The second function is for thread to exit, this is same as the last sentence of `return value`, if `pthread_exit()` is called in the main thread, then `exit()` will not get called, the other thread tend to become a zombie state. These two function provide us a way for different threads to know the state of each other.

###Synchronization




