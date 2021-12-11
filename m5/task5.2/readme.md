# Task 5.2


## Results 

1.
Here is the syntax of an entry in the /etc/passwd file:

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

2.
A UID (user identifier) is a number assigned by Linux to each user on the system. This number is used to identify the user to the system and to determine which system resources the user can access. UIDs are stored in the /etc/passwd file
![image](https://user-images.githubusercontent.com/42848618/145690244-613d3c16-738a-4d4f-9669-7200aee81747.png)
The third field represents the UID. Notice how the root user has the UID of 0. Most Linux distributions reserve the first 100 UIDs for system use. New users are assigned UIDs starting from 500 or 1000. For example, new users in Ubuntu start from 1000.

3.
Groups in Linux are defined by GIDs (group IDs). Just like with UIDs, the first 100 GIDs are usually reserved for system use. The GID of 0 corresponds to the root group and the GID of 100 usually represents the users group. GIDs are stored in the /etc/groups file.
![image](https://user-images.githubusercontent.com/42848618/145690311-02feef3d-6844-439c-8b15-fbec0754790a.png)
The third field represents the GID. New groups are usually assigned GIDs starting from 1000.

4.
Forth field of /etc/passwd contains group ID (GID). Command groups also can determine groups.
![image](https://user-images.githubusercontent.com/42848618/145690420-7c2e7678-2436-4ea9-bb49-a371416bded4.png)

5.
I can add new user used a command adduser and in process creating account you need specify more details of new user, like set a password, full name, room numbers, phones and other.
![image](https://user-images.githubusercontent.com/42848618/145690839-f2d2bee9-b54e-4f13-ae93-b165d62851b2.png)

6. I can change username or user information use command usermod.
![image](https://user-images.githubusercontent.com/42848618/145691048-06d50082-641c-4bd3-91a9-d244d330bde2.png)

7.
Directory /etc/skel/ (skel is derived from the “skeleton”) is used to initiate home directory when a user is first created.
Below is a sample /etc/defualt/useradd file which defines the skel directory. You can change the default location /etc/skel to any other location.
You can also change the default base home directory (which is “/home” in the above example) to any other location.
![image](https://user-images.githubusercontent.com/42848618/145691216-0c6b6bb0-7290-4f2f-86bd-9d69cdc7a2e8.png)


8. Command userdel using for remove user from system include his mailbox.
![image](https://user-images.githubusercontent.com/42848618/145691704-ee207108-41e8-4595-b2fd-4d4f6c99cbac.png)

9. For lock and unlock user accounts used command passwd with keys -l (lock) and -u (unlock).
![image](https://user-images.githubusercontent.com/42848618/145691834-dcb6fc2e-a4f5-404e-8086-c5655c067a54.png)

10. Command passwd -de using for rovide password-free login for subsequent password change.

![image](https://user-images.githubusercontent.com/42848618/145691980-49a5d779-1c90-4a0e-8e59-4b3192e5a16d.png)






