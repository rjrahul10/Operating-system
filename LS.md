# 'ls'

**Description:** The 'ls' command is used in computing world to list the files present in the current working directory.This file wil tell you about the simulation of ls command using system calls.

**ALGORITHM:**

Step 1: First, store the pathname of the current working directory.

Step2: Now scan the directory and sort the resultant array of structure.

Step3: Display the name of member for all entries if it is not a hidden file.

**Example** C Code
```
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
#include<sys/dir.h>
#include<dirent.h>

int file_select(struct dirent *entry)
{
	if((strcmp(entry->d_name, ".")==0||strcmp(entry->d_name, "..")==0))
	return 0;
	else
	return 1;
}
int main()
{	
	struct dirent **files;
	char cwd[1000];
	getcwd(cwd, sizeof(cwd));
	printf("The current working directory is %s\n", cwd);
	int count;
	count = scandir(cwd, &files,file_select, alphasort);
	if(!count)
		printf("There are no files in this directory");
	else
	{	printf("There are %d files in this directory", count);
		int i;
		for(i=1;i<=count;i++)
		printf("%s ", files[i-1]->d_name);
		
	}
	return 0;
}
```
