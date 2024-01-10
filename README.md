Scenario 
There is a customer who came to you with a problem to have a custom linux
command for his operations. Your task is to understand the problem and create a linux
command via bash script as per the instructions.
Command name - internsctl
Command version - v0.1.0# XenonStack---Custom-Linux-Command

""Section A""
1. I want a manual page of command so that I can see the full documentation of the command.
For example if you execute the command
man ls
as output we get the doc and usage guidelines. Similarly if I execute man internsctl I want
to see the manual of my command.

***Ans***
I do not use the `man` command and instead opt for the `cat` command when performing operations on Git Bash.
        $ cat intersctl

<img width="394" alt="Screenshot 2024-01-10 165345" src="https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/d713bd41-e684-4208-a3d2-e41bd7c6860b">
<img width="438" alt="Screenshot 2024-01-10 165537" src="https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/e240b369-f627-42da-8faa-5595f854f1a0">

2. Each linux command has an option --help which helps the end user to understand the use
cases via examples. Similarly if I execute internsctl --help it should provide me the
necessary help
***Ans***
       $ internsctl --help

<img width="387" alt="Screenshot 2024-01-10 165614" src="https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/a752242f-9992-492e-8077-d4b385ee6175">

3. I want to see version of my command by executing
***Ans***   
       $ internsctl --version

<img width="272" alt="Screenshot 2024-01-10 165644" src="https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/7b899787-9111-4371-81d7-3383fe6a4030">

""Section B""
I want to execute the following command for -
Part1 | Level Easy
I want to get cpu information of my server through the following command:

$ internsctl cpu getinfo
Expected Output -
I want similar output as we get from lscpu command
***Ans***
       $ internsctl cpu getinfo

<img width="266" alt="Screenshot 2024-01-10 170259" src="https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/15c013ff-5a79-40d4-a8fa-4ee3b2188109">

I want to get memory information of my server through the following command:
$ internsctl memory getinfo
Expected Output
I want similar output as we get from free command
***Ans***
      $ internsctl memory getinfo
      
<img width="291" alt="Screenshot 2024-01-10 170321" src="https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/e0bf2336-e282-4a64-bb1d-f587d3d17259">

""Part2 | Level Intermediate""
I want to create a new user on my server through the following command:
$ internsctl user create <username>
Note - above command should create user who can login to linux system and access his home
directory
***Ans***
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/5ad0290e-be51-4a2f-b445-77e1ab42d695)

I want to list all the regular users present on my server through the following command:
$ internsctl user list
***Ans***
          $ internsctl user list
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/a152d3dd-1493-4792-8fa4-d90ff96f5cd0)

If want to list all the users with sudo permissions on my server through the following command:
$ internsctl user list --sudo-only
***Ans***
          $ internsctl user list --sudo-only
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/9abef960-6c54-4628-84ad-701d19cc3300)

""Part3 | Advanced Level""
By executing below command I want to get some information about a file
$ internsctl file getinfo <file-name>
Expected Output [make sure to have the output in following format only]
xenonstack@xsd-034:~$ internsctl file getinfo hello.txt
File: hellot.txt
Access: -rw-r--r--
Size(B): 5448
Owner: xenonstack

Modify: 2020-10-07 20:34:44.616123431 +0530

In case I want only specific information then I must have a provision to use options
$ internsctl file getinfo [options] <file-name>
--size, -s to print size
--permissions, -p print file permissions
--owner, o print file owner
--last-modified, m

***Ans***
        $ internsctl file getinfo example.txt
        $ internsctl file getinfo example.txt --permissions --size --owner --last-modified

![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/ffd09e5a-12f6-4067-99f0-c4a21094a622)
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/5c7613cb-79e9-472f-895b-c675cd61fafe)


Expected Output with options
If I want to obtain the size of the specified file only, I should be able to use the following
command:
xenonstack@xsd-034:~$ internsctl file getinfo --size hello.txt
5448

***Ans***
          $ internsctl file getinfo example.txt --permissions
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/0b0a6d06-e0b7-42c5-a61d-543036426a03)

If I want to obtain the permissions of the specified file only, I should be able to use the following
command:
xenonstack@xsd-034:~$ internsctl file getinfo --permissions hello.txt
-rw-r--r--

***Ans***
          $ internsctl file getinfo example.txt --size
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/13d8c5b2-6b99-4e51-b8b9-bb652abf7e29)

If I want to obtain the owner of the specified file only, I should be able to use the following
command:
xenonstack@xsd-034:~$ internsctl file getinfo --owner hello.txt
xenonstack

***Ans***
          $ internsctl file getinfo example.txt --owner
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/d6966826-3a6d-4372-96ba-93e2e2a7388c)

If I want to obtain the last modified time of the specified file only, I should be able to use the
following command:
xenonstack@xsd-034:~$ internsctl file getinfo --last-modified hello.txt
2020-10-07 20:34:44.616123431 +0530

***Ans***
           $ internsctl file getinfo example.txt --last-modified
![image](https://github.com/Tripti-Jain-15/XenonStack---Custom-Linux-Command/assets/129984766/a1f43ac7-b932-4453-b64d-752943f14cfd)




