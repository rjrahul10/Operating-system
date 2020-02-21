# WAIT
**Description:** The wait system call will halt the parent process until child process terminates. After the child process terminates the kernel notifies the parent by sending the SIGCHILD signal to the parent.

**Example** cpp code
```
#include<stdio.h>
#include<sys/types.h>
#include<unistd.h>
int main()
{
	int value;
	value = fork();
	wait(NULL);
	if(value==0)
	printf("Child Process is created with id is  %d and Child Parent Process id is %d\n", getpid(), getppid());
	else if(value<0)
	printf("Process creation is unsuccessful\n");
	else
	printf("Parent Process is created with id is %d and Parent Parent Process id is %d\n", getpid(),getppid());
return 0;
}
```
