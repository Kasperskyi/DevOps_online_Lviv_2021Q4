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
When I used command touch to soft link 
