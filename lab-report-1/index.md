# Lab Report 1

## Command: cd

### No arguments
```console
[user@sahara ~]$ cd
```
This seems to do nothing, however, it changes into the users home directory, which we are already in. 

### Directory path as argument
```console
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
Changes the current working directory to be ~/lecture1.

### File path as argument
```console
[user@sahara ~]$ cd lecture1/Hello.java
bash: cd: lecture1/Hello.java: Not a directory
```
Throws an error since the cd command argument must be a directory path.

## Command: ls

### No arguments
```console
[user@sagara ~]$ ls
Hello.class  Hello.java  messages  README
```
Prints the files and directories under the current working directory.

### Directory path as argument
```console
[user@sahara ~]$ ls messages
en-us.txt  es-mx.txt  fr-be.txt  zh-cn.txt
```
Prints the files and directories under the directory/directories path(s) passed as an argument.

### File path as argument
```console
[user@sahara ~]$ ls Hello.java
Hello.java
```
Prints the name of the file.

## Command: cat

### No arguments
```console
[user@sahara ~]$ cat
  
```
It is not clear here but the program stalls and you have to force close the program.

### Directory path as arugment
```console
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
Throws an error because the cat command argument(s) must be a file path.

### File path as argument
```console
[user@sahara ~]$ cat lecture1/messages/en-us.txt
Hello World!
```
Prints contents of the file.
