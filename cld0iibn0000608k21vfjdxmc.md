---
title: "Shell Scripting Interview
Questions"
datePublished: Tue Jan 17 2023 17:31:44 GMT+0000 (Coordinated Universal Time)
cuid: cld0iibn0000608k21vfjdxmc
slug: shell-scripting-interview-questions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1673969254472/c8980016-150f-45af-835d-d5f243844ab1.jpeg
tags: linux, hashnode, shell-script, kunalkushwaha, wemakedevs

---

---

## Shell Scripting Interview Questions for Freshers

### 1\. What is Shell?

<mark>A Shell is a command-line interpreter between the user and kernel or a complete environment specially designed to run commands, shell scripts, and programs.</mark> In this, whenever a user enters human-readable commands (input commands) through the keyboard, the shell communicates with the kernel to execute these commands, and display output in a shell script. Just as there are different flavors of operating systems, there are also different types of shells. Every shell has its own set of commands and functions. Shells issue the prompt, $, called a command prompt. You can type into the prompt while it is displayed.

After you press enter, your input is read by the shell. Based on the first word of your input, determines the command you want to run. The characters in a word are separated using spaces and tabs.

**Example:**

Here is an example of a date command that displays the current date and time:

```bash
$date Tue Jan 16 06:03:35 MST 2023
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673970319495/9e8451e1-b57d-4931-867c-1289c2b5ad2b.png align="center")

### 2\. What is Shell Scripting?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673970006526/eb26f287-ce0d-4009-bdf8-11180264a59d.png align="center")

<mark>Text files containing commands to execute by a shell are called shell scripts. In this, a long and repetitive series of commands are compiled into a single script that can be stored and executed at any time, thereby reducing programming efforts.</mark> In shell scripts, repetitive work is largely avoided. The most common reason for using shell scripting is to program operating systems of Windows, UNIX, Apple, etc. In addition, companies use this script to develop an operating system with its features. In terms of system-level operations, it is considered to be the easiest programming language to use. A shell script is referred to as a batch file in the DOS operating system, and EXEC in IBM's mainframe VM operating systems. Shell scripts can be used for the following applications:

* Automation of the code compiling process.
    
* Run a program or create an environment for programming.
    
* Complete batch processing and file manipulation.
    
* Integrate existing programs.
    
* Perform routine backups.
    
* Keeping an eye on a system.
    
* System administration's tasks Creating, maintaining, and implementing system boot scripts.
    

**A sample shell script:**

echo "hello world"

**Run it as follows:**

$ bash hello. sh

hello world

### 3\. Why is a shell script needed?

Shell scripts can be written for a variety of reasons:

* Keeping repetitive tasks to a minimum.
    
* Can be used by system administrators for routine backups.
    
* Monitoring the system.
    
* Adding new functions to the shell.
    
* Shell scripting allows you to create your tools.
    
* System admin can automate daily tasks.
    

### 4\. What do you mean by Shell variable?

Shell variables are integral parts of all Shell programs and scripts. In general, we know that variables usually store data either in the form of characters or numbers. Shell also stores and manipulates information using variables in its programs. Generally, shell variables are stored as strings. Variables in the shell provide the information needed for scripts/commands to execute. In the following example, a shell variable is created and then printed:

variable ="Hello"

echo $variable

### 5\. What are the different types of variables mostly used in shell scripting?

Shell scripts usually have two types of variables:

* **System-defined variables:** Also called environment variables, these are special built-in variables in the Linux kernel for each shell. They are normally defined in capital letters by the OS (Linux) and are standard variables.
    
* **Example:** SHELL
    
    It is a Unix Defined or System Variable, which specifies the default working shell.
    
* **User-defined variables:** These variables are created and defined by users to store, access, read, and manipulate data. In general, they are defined in lowercase letters. The Echo command allows you to view them.
    
* **Example:**
    
    $ a=10 In this case, the user has defined the variable ‘a’ and assigned it the value 10.
    

### 6\. Explain ways to create shortcuts in Linux.

**Hard Link:** Hard links are mirror images of the originally linked files and are linked with an inode number. A hard-linked file remains even after the original file is deleted. Since hard links point to inodes, they cannot be implemented on directories. Hard links are created by the following command:

```bash
ln [original filename] [link name]
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673970974762/d62fa0a7-97bb-4822-a620-6e3961e1ef85.png align="center")

* **Soft Link:** Generally, soft links (also referred to as Symbolic links) are linked to the file name and can reside on the same as well as different file systems. When a soft link is created or deleted, it does not affect the original file, but when the original file is deleted, the soft link stops working. Typically, soft links are aliases
    
    (alternative paths) for the original file. Soft links are created by the following
    
    command:
    
    ```bash
    $ ln -s [original filename] [link name]
    ```
    

### 7\. How to check whether a link is a hard one or a soft link?

We can use the -h and -L operators of the test command to check whether a link is hard or soft (symbolic link).

* \-h file //true if the file is a symbolic link
    
* \-L file //true if the file is a symbolic link
    
    One can also use:
    
* **readlink FILE; echo $?** // This returns 1 if it's a hard link and 0 if it's a symbolic link.
    

### 8\. Difference between Hard link and Soft Link.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673971508301/be273b05-c109-4ddc-8851-c02218f26e7f.png align="center")

### 9\. What is the importance of $#?

$# usually holds the number of arguments, although it may be different for functions. To put it simply, it was used to store the number of command-line arguments passed to a shell script.

### 10\. Write the command that is used to execute a shell file.

Firstly, use the chmod command to set execute permission on your script as shown below:

**chmod +x** [**script-name-here.sh**](http://script-name-here.sh)

Secondly, run or execute your script as follows:

**./**[**script-name-here.sh**](http://script-name-here.sh)

Alternatively, you can execute the shell script by:

**sh script-name-here. sh**

### 11\. What is the use of the "$?" command?

By using the command "$?", you can find out the status of the last command executed.

### 12\. What is the best way to run a script in the background?

**Example:**

script. sh &

command &

### 13\. Explain the way you can connect to a database server.

Open client driver comes with the isql utility that can be used to connect to a database server from Linux. Here's how to do it:

**isql –S serverName –U username –P password**

### 14\. What is a file system? Write down the four core components of a Linux file system.

Generally, file systems are referred to as collections of files, which include information related to those files. It would be impossible to tell where one piece of data stops and the next begins without a file system.

There are four blocks in a file system:

* **Super Block:** A superblock contains information about a file system, including block size, group size, usage statistics, empty/filled blocks, inode table size & location, and so on. One of the tools used to describe a file system, along with inodes, entries, and files, is the superblock. Multiple superblocks are created with the file system, as the superblock contains critical information.
    
* **Boot Block:** Located on the disk label, a boot block is a special set of blocks that contains data or information on the disk layout. Normally, this block contains the bootstrap loader program, which a user runs upon launching the host computer. The boot block remains blank if the file system is not used for boot.
    
* **Data Block:** Also called storage blocks, data blocks contain the remainder of the space allocated to the file system. The data block's size is measured at the time of file system creation. For a regular file, the content of files is contained in the data blocks. For directories, the inode number and file name of the files are contained in the data blocks.
    
* **Inode:** Inodes contain information about each file in the filesystem. Normally, an inode doesn't contain a file's name, which is located in a directory instead. An inode contains information such as the type of file, the permission bits, the owner, the group, the file size, and the time when the file was modified.
    

### 15\. Name the alternative command for echo.

<mark>The </mark> **<mark>tput</mark>** <mark> command is an alternative command for </mark> **<mark>echo</mark>**<mark>.</mark> We can use this command to control how the output is displayed. Additionally, shell scripts can do things such as underline text and center text, regardless of the size of the screen.

---

## Shell Scripting Interview Questions for Experienced

### 1\. What do you mean by crontab?

Crontab stands for "cron table," meaning that it makes use of the cron scheduler to perform tasks. In other words, it is the list of commands that you wish to run on a regular schedule and the command that will let you manage it. It is possible to view or edit the table of commands using the crontab command. In addition to the schedule, the term "Crontab" also refers to the name of the program used to edit the schedule.

### 2\. Name two files of the crontab command.

**<mark>cron. deny and cron. allow</mark>** <mark> two files in the /etc/cron.d directory that controls access to the crontab command. Crontab command tasks such as creating, editing, displaying, or removing crontab files are relegated to specific users through these files.</mark> Both files usually consist of a list of user names, one user name per line. Together, these access control files perform the following functions:

* **cron.allow** decides which users are allowed to run the crontab command.
    
* **cron.deny** decides which users are denied from using the crontab command.
    
* When **cron.allow or cron.deny** doesn't exist, superuser privileges are required to run it.
    

### 3\. Name the command that is used to take the backup.

<mark>The backup is taken using the </mark> **<mark>tar command</mark>**. **Tar is an acronym** for tape archive and is used to create backups using **tar, gzip, and bzip**. Files can be saved and restored from and to a tape using this command. In this, files and directories are generally compressed into tarballs, an archive file. For this purpose, it is among the most widely used commands. Furthermore, the tarball can be easily moved from one server to another.

### 4\. Write down the Syntax for all the loops in Shell Scripting.

In shell scripting, you can use three looping statements as given below:

* while statement
    
* for statement
    
* until statement
    

**The syntax is as follows:**

* **For Loop:** <mark>Loops that operate on lists of items are known as loops. Each item in the list receives the same set of commands</mark>.
    
    **Syntax:**
    
    ```bash
    for var in word1 word2 ... wordN
    do
    Statement to be executed
    done
    ```
    
    **Example:**
    
    ```bash
    for a in 1 2 3 4 5 6 7 8 9 10
    do
    if [ $a == 3 ]
    then
    break
    fi
    echo "Iteration no $a"
    done
    ```
    
    **OUTPUT:**
    
    ```bash
    $bash -f main.sh
    Iteration no 1
    Iteration no 2
    ```
    
* **While Loop:** <mark>It involves evaluating a command first and then executing a loop based on the result. The loop will be terminated if the command raises to false.</mark>
    
    **Syntax:**
    
    ```bash
    while command
    do
    Statement to be executed
    done
    ```
    
    **EXAMPLE:**
    
    ```bash
    a=0
    while [ $a -lt 3 ]
    do
    echo $a
    a=`expr $a + 1`
    done
    ```
    
    **OUTPUT:**
    
    ```bash
    $bash -f main.sh
    0
    1
    2
    3
    ```
    
* **Until Loop:** <mark>As often as the condition/command evaluates to false, the until loop</mark>
    
    <mark>is executed. Once the condition or command becomes true, the loop terminates</mark>.
    
    SYNTAX:
    
    ```bash
    until command
    do
    
    Statement to be executed until command is true
    
    done
    ```
    
    **EXAMPLE:**
    
    ```bash
    a=0
    until [ $a -gt 3 ]
    do
    echo $a
    a=`expr $a + 1`
    done
    ```
    
    **OUTPUT:**
    
    ```bash
    $bash -f main.sh
    0
    1
    2
    3
    ```
    

### 5\. What do you mean by the “s” permission bit in a file?

<mark>The SUID (Set User ID) bit is known as the "s" bit. SUIDS are special file permissions for executable files that enable other users to run the file as the file owner.</mark> There will be an s (to indicate SUID) special permission for the user instead of the normal x, which represents execute permissions. A file that has the "s" bit set will grant the process the rights of the file's owner while the program is running.

EXAMPLE:

Executing the "passwd" command to change the password, for example, allows the user to write the new password to the shadow file even though its owner is "root".

### 6\. How will you debug a shell script?

With set, you can turn on or off debugging options in the shell:

* **Set -x:** This displays commands and their arguments as they are being executed. **Set -v:** It displays shell input lines in real-time as they are read.
    

### 7\. What is the importance of the sed command and awk command?

* **sed Command:** <mark>sed command is an acronym for stream editor. It is used for editing a file without using an editor.</mark> The SED command performs a variety of operations on files, such as searching, finding and replacing, inserting and deleting. However, substitution or find and replace are the most commonly used features of SED.
    
* **Syntax:** sed options file
    
* **Example:** Execution over Shell Interpreter/Editor
    
    ```bash
    /u/user1/Shell_Scripts_2020> echo "Hi BISWAJIT" | sed 's/Hi/Hello/'
    ```
    
    In this case, the “s” command in sed replaces the string Hi with “Hello”.
    
    **OUTPUT**:
    
    ```bash
    Hello BISWAJIT
    ```
    
* **awk Command:** <mark>The command is a scripting language generally used to manipulate data and generate reports</mark>. There is no need to compile it and users are allowed to have access to a variable, string functions, numeric functions, and logical operations.
    
* **Syntax:** awk options File Name
    
* **Example**: Script/Code
    
    ```bash
    /u/user1/Shell_Scripts_2017> cat > script10
    Hello Sita
    Hello Rudra
    Hello Biswa
    ```
    
    An awk command/utility assigns variables in the following way:
    
* $0 -&gt; For the whole line (e.g. Hello Biswa)
    
* $1 -&gt; For the first field i.e. Hello
    
* $2 -&gt; For the second field
    
    **Execution over Shell Interpreter/Editor**
    
    ```bash
    awk ‘{print $0}’ script10
    ```
    
    The above script prints all the 3 lines completely.
    
    **OUTPUT:**
    
    ```bash
    Hello Sita
    Hello Rudra
    Hello Biswa
    ```
    
    **Execution over Shell Interpreter/Editor**
    
    ```bash
    awk ‘{print $1}’ script10
    ```
    
    The above script prints only the first word i.e., Hello from each line.
    
    **OUTPUT:**
    
    ```bash
    Hello
    Hello
    Hello
    ```
    

### 8\. Name different commands that are available to check the disk usage.

* df – It is used to find out how much space is left on a disk.
    
    du – With this command, you can find out how much disk space the specified files and each subdirectory take up.
    
* dfspace – Using this command, you can check the amount of free disk space in MB.
    

### 9\. Write the difference between grep and find commands.

* **Grep command:** <mark>This command facilitates searching and displaying content based on regular expressions specified by the user. Using the Grep command, one can search in a file for patterns.</mark>
    
* The **grep** command has the following syntax:
    
    **grep “literal string” &lt;fileName&gt;**
    
    **EXAMPLE:**
    
    ```bash
    grep "apple" file1.txt //Displays all the lines with the word "apple"
    grep "apple" file1.txt file2.txt //Scan multiple documents and search the word "apple"
    ```
    
* **Find command:** <mark>The </mark> **<mark>FIND</mark>** <mark> command searches for files and folders based on their size, modification time, and access time. You can use this command to search files and directories.</mark> Find command has the following syntax: **find&lt;path&gt; &lt;search criteria&gt; &lt;action&gt;**
    
* **Example**:
    
    ```bash
    find –type f               // Command will find all the files
    find –type d              //Command will find all the directories
    find . –name file1.txt   //Command will find file1.txt in the current directory.
    ```
    
    ### 10\. How can we create a function in the shell script?
    
    In other programming languages, shell functions are much like subroutines, procedures, and functions. The syntax for declaring a function is as follows:
    

```bash
function_name ()
{
list of commands
}
```

Function\_name is the name of your function, and that's what you'll use to call it from anywhere in your script. The function name must be followed by parentheses, then a list of commands enclosed in braces.

**EXAMPLE:**

```bash
#!/bin/sh
# Define your function here
Hello ()
{
echo "Hello World"
}
# Invoke your function
Hello
```

The following output will be displayed after execution:

```bash
$./test.sh
Hello World
```

### 11\. How to use pipe commands?

<mark>Pipe command allows you to use several commands in the same way, in which the output of one is used as input for another.</mark> Like a pipeline, each process output is directly inputted to the next one. A pipe is represented by the symbol "|". The flow of data through a pipeline is unidirectional, i.e., from left to right.

**Syntax :**

```bash
command_1 | command_2 | command_3 | .... | command_N
```

### 12\. Name the command that is used to compare the strings in a shell script.

<mark>To compare text strings, use the </mark> **<mark>test</mark>** <mark> command. By comparing each character in each string, the </mark> **<mark>test</mark>** <mark> command usually compares text strings. In most cases, tests are generally included as a conditional execution of shell commands.</mark> It can be used for:

* Comparison of file attributes
    
* Comparison of strings
    
* Comparing basic arithmetic operations
    
    Using square brackets (\[ and \]) around the EXPRESSION is equivalent to testing it with the test.
    
    **Syntax of test command:**
    
* test EXPRESSION
    
* test EXPRESSION && true-command
    
* test EXPRESSION || false-command
    
* test EXPRESSION && true-command || false-command
    
    **EXAMPLES:**
    
* test 50 -gt 40 && echo "Yes" || echo "No"
    
    Because 50 is greater than 40, this command prints the text "Yes".
    
* \["Excellent" = "Excellent"\]; echo $?
    
* As the two strings are identical, this command prints "0" because the expression is true.
    

---

# Conclusion

You can automate a lot of repetitive manual tasks with shell scripting, which is an easy and powerful programming method. Modern programming languages offer many of the features that make them appealing to programmers. DevOps engineers and automation testers often find this concept vital in preparing for interviews. Shell scripting allows the development of simple to complex scripts. Several daily tasks can be automated using shell scripting as well. We thought of making your job easier by putting together an ensemble of the most frequently asked interview questions and sample answers on shell scripting. These interview questions will help you understand that a shell is an interface between the user and the operating system, which interprets user commands to be executed by the kernel or operating system.