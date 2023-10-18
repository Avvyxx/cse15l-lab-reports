# Lab Report 1: Remote Access and FileSystem

For this lab, I will use the `pwd` command for every display to show the current working directory. However it is worth noting that the path after `<user name>@<computer name>` on each command prompt indicates the current working directory (`[user@sahara ~]`), and ~ indicates the home directory.

## Command: `cd`

### No arguments
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd
```
This seems to do nothing, however, it changes into the users home directory, which we are already in, `/home`.

### Directory path as argument
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
Changes the current working directory to be `~/lecture1`, which has the absolute path of `/home/lecture1`.

### File path as argument
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/Hello.java
bash: cd: lecture1/Hello.java: Not a directory
```
Throws an error since the cd command argument must be a directory path.

## Command: `ls`

### No arguments
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls
Hello.class  Hello.java  messages  README
```
Prints the files and directories under the current working directory.

### Directory path as argument
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls messages
en-us.txt  es-mx.txt  fr-be.txt  zh-cn.txt
```
Prints the files and directories under the directory/directories path(s) passed as an argument.

### File path as argument
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls Hello.java
Hello.java
```
Prints the name of the file.

## Command: `cat`

### No arguments
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat
Hello!
Hello!


World!
World!
```
When provided with no arguments the program will output any input provided to it indefinitely. The program will not close on it's own so you would have to end it with `ctrl + c`.

### Directory path as arugment
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
Throws an error because the cat command argument(s) must be a file path.

### File path as argument
```console
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1/messages/en-us.txt
Hello World!
```
Prints contents of the file.

---

[Back to homepage](https://avvyxx.github.io/cse15l-lab-reports/)
