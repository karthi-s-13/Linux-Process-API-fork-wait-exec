# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec() 

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

Developed by : KARTHIKEYAN S

Register Number : 212224230116

## C Program to print process ID and parent Process ID using Linux API system calls
~~~
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
~~~

## OUTPUT
![323363651-277a5ef9-b0c2-4e5b-ad59-4a415db2c31c](https://github.com/user-attachments/assets/6dffb9f6-4fb8-4202-ac89-89b35803df0f)


## C Program to create new process using Linux API system calls fork() and exit()
~~~
#include <stdio.h>
#include<stdlib.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
~~~

<br>
<br>
<br>
<br>
<br>


## OUTPUT
![323363997-88cf0f5e-c8fc-4341-b71a-c87c6979fdf1](https://github.com/user-attachments/assets/4fa7b882-4a81-4933-9f31-0d57535d10eb)


## C Program to execute Linux system commands using Linux API system calls exec() family
~~~
#include <unistd.h>
#include <stdio.h>
#include <stdlib.h>
int main()
{
	printf("Running ps with execlp\n");
	execlp("ps", "ps", "ax", NULL);
	printf("Done.\n");
	exit(0);
}
~~~

## OUTPUT
![323364224-1842c773-69d6-4a4d-9e90-fd5f92813952](https://github.com/user-attachments/assets/66153550-2e6b-42cd-b96b-b7579d2c43c2)


# RESULT:
The programs are executed successfully.
