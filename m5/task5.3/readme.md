# Task 5.3


## Results of Part 1

**1.**  Here are the different values that the s, stat and state output specifiers (header "STAT" or "S") will display to describe the state of a process.

       D    Uninterruptible sleep (usually IO)
       I    Idle kernel thread
       R    Running or runnable (on run queue)
       S    Interruptible sleep (waiting for an event to complete)
       T    Stopped, either by a job control signal or because it is being traced.
       t    Stopped by debugger during the tracing.
       W    paging (not valid since the 2.6.xx kernel)
       X    dead (should never be seen)
       Z    Defunct ("zombie") process, terminated but not reaped by its
            parent.
            
For BSD formats and when the stat keyword is used, additional characters may be displayed:

       <    high-priority (not nice to other users)
       N    low-priority (nice to other users)
       L    has pages locked into memory (for real-time and custom IO)
       s    is a session leader
       l    is multi-threaded (using CLONE_THREAD, like NPTL pthreads do)
       +    is in the foreground process group



**2.** Command "pstree" display a tree of processes.

![image](https://user-images.githubusercontent.com/42848618/145881162-399016de-bcd3-4fa3-b695-c7cdd11be493.png)



**3.** The proc file system is a pseudo-file system which is used as an interface to kernel data structures. It is commonly mounted at /proc. Most of it is read-only, but some files allow kernel variables to be changed.



**4.** Command "cat /proc/cpuinfo" display informations about CPU.

![image](https://user-images.githubusercontent.com/42848618/145882079-a543811c-d9c1-4f0c-8359-d2801e533541.png)



**5.**

![image](https://user-images.githubusercontent.com/42848618/145884222-b8e7ee40-82d0-47d5-8294-89b6a4c3ee41.png)



**6.**
Kernel processes:

![image](https://user-images.githubusercontent.com/42848618/145886031-26ad25e3-0332-420b-ac1b-180dfd036800.png)

Users processes:

![image](https://user-images.githubusercontent.com/42848618/145886071-5d0d1fac-90d0-4bba-81b7-8af36ee1375f.png)



**7.**

![image](https://user-images.githubusercontent.com/42848618/145886700-f4369784-741b-4037-a7dc-85af3bb7fdc8.png)

I    Idle kernel thread
S    Interruptible sleep (waiting for an event to complete)
<    high-priority (not nice to other users)
s    is a session leader



**8.** 
 
![image](https://user-images.githubusercontent.com/42848618/145887779-524177f3-ca7d-4fbb-b2d8-364da61a428f.png)



**9.** "man ps" propose using pgrep, pstree, top, proc

![image](https://user-images.githubusercontent.com/42848618/145888470-c2f5225a-62a4-4f09-9d2d-fec0a7abc806.png)



**10.** Command "top" displaying running processes in real time.

![image](https://user-images.githubusercontent.com/42848618/145888750-0d348197-507a-42fc-905f-44ea396bbeb6.png)



**11.** 

![image](https://user-images.githubusercontent.com/42848618/145888984-6d4f52c2-a500-4c67-ae4c-9ed01c4580a2.png)



**12.** See below couple keys of command "top": 
-b  :Batch-mode operation
    Starts top in Batch mode, which could be useful for sending output from top to other programs or to a file.  In this mode, top will not accept input and runs until the iterations limit you've set with the `-n' command-line option or until killed.
-E  :Enforce-Summary-Memory-Scaling as:  -E  k | m | g | t | p | e
    Instructs top to force summary area memory to be scaled as:
    k - kibibytes
    m - mebibytes
    g - gibibytes
    t - tebibytes
    p - pebibytes
    e - exbibytes
-n  :Number-of-iterations limit as:  -n number
    Specifies the maximum number of iterations, or frames, top should produce before ending.
-s  :Secure-mode operation
    Starts top with secure mode forced, even for root.  This mode is far better controlled through a system configuration file (see topic 6. FILES).
-u | -U  :User-filter-mode as:  -u | -U number or name
    Display only processes with a user id or user name matching that given.  The `-u' option matches on  effective user whereas the `-U' option matches on any user (real, effective, saved, or filesystem).
    Prepending an exclamation point (`!') to the user id or name instructs top to display only processes with users not matching the one provided.
  


**13.** 

![image](https://user-images.githubusercontent.com/42848618/145892045-f3a7f030-1ec2-4b17-bd89-4454b16fdfd7.png)

Sort by CPU Time

![image](https://user-images.githubusercontent.com/42848618/145892167-10eab7d1-f7df-4e55-9a3a-9bdd1440acf8.png)

Sort by PID

![image](https://user-images.githubusercontent.com/42848618/145892393-3b47f6e6-6b53-43ca-b587-bcef0e36e170.png)



**14.** Sometimes you might want to change the priority of a process in Linux. For example, you might run a process that is very important and you want it to finish quickly. You can change the process priority using the nice command and give that process more CPU time.
Every process running on your system has a nice value. By default, the nice value is set to 0. The process priority range is from -20 to 19.
Here are a few facts about changing the priority of a process:
- the lower number is better (the process with the lower number will get more CPU time).
- a regular user can set nice values only from 0 to 19 and only on the its own processes.
- a regular user can set the nice value only higher, not lower.

Commands:
set priority for new process
nice -n 10 mysql-server
for existing process.
renice 5 -p $(pgrep mysql-server)



**15.** Key "r" can change a priority in top. Then you need to enter PID and the value of nice.

![image](https://user-images.githubusercontent.com/42848618/145895585-2363df99-a106-4b34-b23d-6276cec841ad.png)

![image](https://user-images.githubusercontent.com/42848618/145895622-23082c18-9dc4-4a5b-92a9-55a14b6fc20f.png)

![image](https://user-images.githubusercontent.com/42848618/145895679-45147e18-786a-4129-a5dd-88b446185c9d.png)



**16.** Command "kill -l" display all the available signals you can use.

![image](https://user-images.githubusercontent.com/42848618/145896008-f9e21e5f-0d64-4869-b127-fe9fd5c5fa68.png)

The most common kill signals are:

SIGHUP (1) - Hangup
SIGINT (2) - Interrupt from keyboard
SIGKILL (9) - Kill signal
SIGTERM (15) - Termination signal
SIGSTOP (17, 19, 23) - Stop the process

Command: kill -9 PID



**17.**  

