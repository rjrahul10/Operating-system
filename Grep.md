# GREP

**Description:** The 'grep' command in the UNIX searches of the patterns, characters in a file. When it matches with the expression in the file, it displays all the lines that have the pattern.

**ALGORITHM**

Step1: Get the filename and the search string from the user.

Step2: Now open the file using system call.

Step3: If file doesnot exist, go to end

Step4: If file exist, read line by line and search for the pattern.

Step5: If pattern matches, display the whole line.

**Example** C code

```
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
#include<sys/types.h>
#include<fcntl.h>
#include<sys/dir.h>
#include<dirent.h>
int main(int argc, char **argv)
{
	char line[100],temp;
	int i,fd;
	fd = open(argv[1], O_RDONLY);
	if(fd)
	{	i=0;
		while(read(fd, &temp, sizeof(char))!=0)
		{
			if(temp!='\n')
			{
				line[i] =temp;
				i++;
			}
			else
			{	if(strstr(line, argv[2])!=NULL)
					printf("%s\n",line);
				memset(line, 0, sizeof(line));
				i =0;
			}			
		}	
	}
return 0;
		
}
```
