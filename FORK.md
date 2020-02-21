# FORK

 **Description:** The Fork system call is used to create a new process called child process. The child process is an exact copy of the parent process. The return value of Fork() is '0' for child process 'Positive' for parent process and 'Negative' if the process creation fails.

 **Eample** code in c
 
 ```
    #include<stdio.h>
    #include<sys/types.h>
    #include<unistd.h>
    int main()
    {
	    int value;
	    value = fork();
	    if(value==0)
	          printf("Child Process is created with id is  %d and Child Parent Process id is %d\n",getpid(), getppid());
	    else if(value<0)
	          printf("Process creation is unsuccessful\n");
	    else
	          printf("Parent Process is created with id is %d and Parent Parent Process id is %d\n",getpid(), getppid());
        return 0;
    }
```
