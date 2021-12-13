# Task 5.2


## Results 

**1)** Here is the syntax of an entry in the /etc/passwd file:

username:password:UID:GID:comment:home directory:default shell

Here is a description of each field:
username – the name of the user.
password – this field has traditionally been reserved for the password. Most Linux distributions, however, store passwords in /etc/shadow. This field is usually set to x, which means that shadow passwords are in use. If the field is set to asterisk (*) it means that the account has no password configured. If the field is set to the exclamation mark (!), the account is locked.
UID – user identifier. It is a unique number representing the user.
GID – the default (primary) login group ID. Users have only one primary group and that group is the group owner for all new files the user creates.
comment – this field contain information about the user. Usually holds the user’s full name.
home directory – the absolute path to the user’s home directory.
default shell – the user’s default shell.

![image](https://user-images.githubusercontent.com/42848618/145689087-6e862f22-1f80-42a0-9a94-a5faf39b7d72.png)

Here is how an entry in the /etc/group file looks like:

group name:password:GID:list of users

![image](https://user-images.githubusercontent.com/42848618/145689095-34f9b282-6014-4a19-a050-9c391b877df1.png)

Pseudo users are accounts for running applications or files. For example, daemon, proxy, syslog, mail, sync.



**2)** A UID (user identifier) is a number assigned by Linux to each user on the system. This number is used to identify the user to the system and to determine which system resources the user can access. UIDs are stored in the /etc/passwd file.

![image](https://user-images.githubusercontent.com/42848618/145690244-613d3c16-738a-4d4f-9669-7200aee81747.png)

The third field represents the UID. Notice how the root user has the UID of 0. Most Linux distributions reserve the first 100 UIDs for system use. New users are assigned UIDs starting from 500 or 1000. For example, new users in Ubuntu start from 1000.



**3)** Groups in Linux are defined by GIDs (group IDs). Just like with UIDs, the first 100 GIDs are usually reserved for system use. The GID of 0 corresponds to the root group and the GID of 100 usually represents the users group. GIDs are stored in the /etc/groups file.

![image](https://user-images.githubusercontent.com/42848618/145690311-02feef3d-6844-439c-8b15-fbec0754790a.png)

The third field represents the GID. New groups are usually assigned GIDs starting from 1000.



**4)** Forth field of /etc/passwd contains group ID (GID). Command "groups" also can determine groups.

![image](https://user-images.githubusercontent.com/42848618/145690420-7c2e7678-2436-4ea9-bb49-a371416bded4.png)



**5)** I can add new user used a command "adduser" and in process creating account you need specify more details of new user, like set a password, full name, room numbers, phones and other.

![image](https://user-images.githubusercontent.com/42848618/145690839-f2d2bee9-b54e-4f13-ae93-b165d62851b2.png)



**6)** I can change username or user information use command "usermod".

![image](https://user-images.githubusercontent.com/42848618/145691048-06d50082-641c-4bd3-91a9-d244d330bde2.png)



**7)** Directory /etc/skel/ (skel is derived from the “skeleton”) is used to initiate home directory when a user is first created.
Below is a sample /etc/defualt/useradd file which defines the skel directory. You can change the default location /etc/skel to any other location.
You can also change the default base home directory (which is “/home” in the above example) to any other location.

![image](https://user-images.githubusercontent.com/42848618/145691216-0c6b6bb0-7290-4f2f-86bd-9d69cdc7a2e8.png)



**8)** Command "userdel" using for remove user from system include his mailbox.

![image](https://user-images.githubusercontent.com/42848618/145691704-ee207108-41e8-4595-b2fd-4d4f6c99cbac.png)



**9)** For lock and unlock user accounts used command "passwd" with keys -l (lock) and -u (unlock).

![image](https://user-images.githubusercontent.com/42848618/145691834-dcb6fc2e-a4f5-404e-8086-c5655c067a54.png)



**10)** Command passwd -de using for rovide password-free login for subsequent password change.

![image](https://user-images.githubusercontent.com/42848618/145691980-49a5d779-1c90-4a0e-8e59-4b3192e5a16d.png)



**11)** In screenshot we can see follow fields:
1. index node
2. file permissions 
3. number of (hard) links
4. owner name
5. owner group
6. file size in bytes
7. time of last modification 
8. file/directory name
 
![image](https://user-images.githubusercontent.com/42848618/145862108-a3f33b9f-b721-421c-af70-7b166f3d76db.png)



**12)** Each file and directory has three user based permission groups:
-|rwx|rw-|r--|
   u   g   o
owner (u) – The Owner permissions apply only the owner of the file or directory, they will not impact the actions of other users.
group (g) – The Group permissions apply only to the group that has been assigned to the file or directory, they will not effect the actions of other users.
other (o) – The other permissions apply to all other users on the system.

Each file or directory has three basic permission types:

read (r, in binary 4) – The Read permission refers to a user’s capability to read the contents of the file.
write (w, in binary 2) – The Write permissions refer to a user’s capability to write or modify a file or directory.
execute (x, in binary 1) – The Execute permission affects a user’s capability to execute a file or view the contents of a directory.
"-"(in binary 0) - mean no special permissions 



**13)** First, determine the rights of the owner, then group rights, and finally, the rights of others.



**14)** Command "chown" using for change owner of file or directory. Command "chmod" using for change the access mode of file/directory. 

![image](https://user-images.githubusercontent.com/42848618/145867243-9da7e688-27ac-4deb-89bd-789002c5944e.png)



**15)** The first number represents the Owner permission; the second represents the Group permissions; and the last number represents the permissions for all other users. The numbers are a binary representation of the rwx string.
r = 4
w = 2
x = 1
You add the numbers to get the integer/number representing the permissions you wish to set. You will need to include the binary permissions for each of the three permission groups.

UMASK in a Linux system stands for User Mask. It is the default permission of a file or directory when they are created in your Linux machine.
Most Linux distros have a default value of UMASK is 022.
The minimum and maximum values of umask for a directory are 000 and 777 respectively. The minimum and maximum values of umask for a file are 000 and 666 respectively. The following table describes some of the common values:

0 - Read, Write & Execute
1 - Read & Write
2 - Read & Execute
3 - Read Only
4 - Write & Execute
5 - Write Only
6 - Execute Only
7 - No Permissions
Exsample of command: umask 077



**16)** A Sticky bit is a permission bit that is set on a file or a directory that lets only the owner of the file/directory or the root user to delete or rename the file. No other user is given privileges to delete the file created by some other user. Sticky Bit is mainly used on folders in order to avoid deletion of a folder and it’s content by other users though they having write permissions on the folder contents.

![image](https://user-images.githubusercontent.com/42848618/145870801-071864b8-17f0-4fa3-9308-bfff534f0a16.png)



**17)** The files and directories can have following attributes:
a - append only: this attribute allows a file to be added to, but not to be removed. It prevents accidental or malicious changes to files that record data, such as log files.
c - compressed: it causes the kernel to compress data written to the file automatically and uncompress it when it’s read back.
d - no dump: it makes sure the file is not backed up in backups where the dump utility is used
e - extent format: it indicates that the file is using extents for mapping the blocks on disk.
i - immutable: it makes a file immutable, which goes a step beyond simply disabling write access to the file. The file can’t be deleted, links to it can’t be created, and the file can’t be renamed.
j - data journaling: it ensures that on an Ext3 file system the file is first written to the journal and only after that to the data blocks on the hard disk.
s - secure deletion: it makes sure that recovery of a file is not possible after it has been deleted.
t - no tail-merging: Tail-merging is a process in which small data pieces at a file’s end that don’t fill a complete block are merged with similar pieces of data from other files.
u - undeletable: When a file is deleted, its contents are saved which allows a utility to be developed that works with that information to salvage deleted files.
A - no atime updates: Linux won’t update the access time stamp when you access a file.
D - synchronous directory updates: it makes sure that changes to files are written to disk immediately, and not to cache first.
S - synchronous updates: the changes on a file are written synchronously on the disk.
T - and top of directory hierarchy: A directory will be deemed to be the top of directory hierarchies for the purposes of the Orlov block allocator.

Command lsattr show attributes of file or directory.

![image](https://user-images.githubusercontent.com/42848618/145871582-f951701e-0ac4-47ae-9ecf-5c72051c74f7.png)

