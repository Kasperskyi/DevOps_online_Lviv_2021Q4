# Task 5.1


## Results of Part 1

I changed the password for user nazar. Command passwd modify /etc/shadow file to change password. 
![Screenshot_37](https://user-images.githubusercontent.com/42848618/144720955-c0511c89-f827-4a75-bf99-67e776f788bb.jpg)
See the some screenshots attached.

I determined the users registered in the system.
The following entries are displayed for each user: login name, the tty name, the remote host, login time, idle time, JCPU, PCPU, and the command line of their current process. The JCPU time is the time used by all processes attached to the tty. It does not include past background jobs but does include currently running background jobs. The PCPU time is the time used by the current process, named in the “what” field.
![image](https://user-images.githubusercontent.com/42848618/144724834-f3f49e4c-ae89-4a49-8884-5b6569425676.png)

I changed information of my account.
![image](https://user-images.githubusercontent.com/42848618/144725261-baec22d9-d84a-41d5-873e-b822b41486fa.png)

Command man -V display version information
Command man -k man - display list of commands or descriptions which have part man.
![image](https://user-images.githubusercontent.com/42848618/144739486-2177585f-9487-41bb-80f1-bdf835ccac00.png)

I explored the more and less commands using the help system.
![image](https://user-images.githubusercontent.com/42848618/144740044-1cab3266-9a83-4618-bcf9-7b2378d4dea4.png)


## Results of Part 2

1. I used command tree and explored it option.
![image](https://user-images.githubusercontent.com/42848618/144741574-cc49b081-8925-4fdc-ba68-b3f0056d6961.png)

2. I used command file to determining file type.
![image](https://user-images.githubusercontent.com/42848618/144742490-ed795719-abb8-4012-a58f-e72c6f3d7d49.png)

3. I used commands cd ~ or cd /home/nazar/ to go back to my home directory.

4. ls -a - this command show all files, directiry and hidden files.
   ls -l - this command show date of update, user permissions, file owner, group, and size of the file in bytes.

5.![image](https://user-images.githubusercontent.com/42848618/144743604-d9fed35b-593a-427c-86fe-044336d32e4f.png)
![image](https://user-images.githubusercontent.com/42848618/144743616-5b0eb85e-c51a-457e-ab91-8f75e458a35a.png)
![image](https://user-images.githubusercontent.com/42848618/144743672-5824670f-7953-4d5d-9b4e-6f64765ca402.png)

6. A soft link is an actual link to the original file, whereas a hard link is a mirror copy of the original file. If you delete the original file, the soft link has no value, because it points to a non-existent file.
![image](https://user-images.githubusercontent.com/42848618/144744265-214f136d-d201-4ee4-a76c-105491d4ddac.png)
When I used command touch to soft link I updated time of original file and also hard link as a mirror of original file.
I deleted labwork2. In result soft link is inactive and hard link saved all information of original file.
7. I installed locate to my Ubuntu and updated db.
![image](https://user-images.githubusercontent.com/42848618/144766445-9e56b581-9856-4d97-938c-523d18394f2c.png)

8. I used command df to show mounted partitions.
![image](https://user-images.githubusercontent.com/42848618/144766496-25203d35-a129-49d6-907e-62c47c428677.png)

9. ![image](https://user-images.githubusercontent.com/42848618/144766673-705f9627-9458-438d-9b5c-2d076b6e1837.png)

10. ![image](https://user-images.githubusercontent.com/42848618/144766950-09e36e7e-9f8f-4d21-bc91-c823dc28385b.png)

11. ![image](https://user-images.githubusercontent.com/42848618/144766998-8166e88d-4628-4008-9dba-4bbdaccfc453.png)

12. ![image](https://user-images.githubusercontent.com/42848618/144767335-9e1a8019-cae8-492c-82a6-6acab1fa6503.png)

13. Command ls -l show type of the device files, which are denoted as the following:
c - character
b - block
p - pipe
s - socket

**Block Device**
These devices transfer data, but in large fixed-sized blocks. You'll most commonly see devices that utilize data blocks as block devices, such as harddrives, filesystems, etc.

**Pipe Device**
Named pipes allow two or more processes to communicate with each other, these are similar to character devices, but instead of having output sent to a device, it's sent to another process.

**Socket Device**
Socket devices facilitate communication between processes, similar to pipe devices but they can communicate with many processes at once.
![image](https://user-images.githubusercontent.com/42848618/145189060-3ca211e2-5689-4a13-9c06-683f1608eb60.png)

14 
| symbol | name | description |
| --- | ------------------ | --------------------- |
| "-" | Ordinary or regular files | Contain data of various content types such as text, script, image, videos, etc. |
| "d" | Directory files	| Contain the name and address of other files. |
| "b" | Block or character special files | Represent device files such as hard drives, monitors, etc. |
| "l" | Link files | Point or mirror other files |
| "s" | Socket files | Provide inter-process communication |
| "p" | Named pipe files | Allow processes to send data to other processes or receive data from other processes. | 

Follow commands show type of files:

ls -l | grep ^- 

ls -l | grep ^d

ls -l | grep ^b

ls -l | grep ^l

ls -l | grep ^s

ls -l | grep ^p

or 

file /dev/sdb1 

15. Command "ls -1lr | tail -5" show 5 last used directory.
![image](https://user-images.githubusercontent.com/42848618/145198834-51b34521-aed5-4afa-9180-23e6f2c80181.png)

