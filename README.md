# File-Permissions-in-Linux

-The following code demonstrates how I used Linux commands to determine the existing
permissions set for a specific directory in the file system.

<p align="center">
Check file and directory details: <br/>
<img src="https://i.imgur.com/dSUwxLs.png" height="80%" width="80%" alt="File-Permissions-in-Linux"/>
<br />
<br />

- The screenshot's first line captures the command I typed, and the rest lay out what the output was. I use the ls command with the -la option to get the file content with the hidden files. The output shows that that where is a directory nameed "drafts" and a hidden file named ".project_x.txt" and a then five other project files. 

<p align="center">
Describeing the permissions string: <br/>

- There are 10-character string can be deconstructed to determine who is authorized to access the
file and their specific permissions. The characters and what they represent are as follows:
- 1st character: This character would either a (d) or hyphen (-) and indicates the file type. If it’s
a (d), it’s a directory. If it’s a hyphen (-), it’s a regular file.
- 2nd-4th characters: These characters indicate the read (r), write (w), and execute (x)
permissions for the USER. When one of these characters is a hyphen (-) instead, the permission is not granted to the user.
- 5th-7th characters: These characters indicate the read (r), write (w), and execute (x)
permissions for the GROUP. When one of these characters is a hyphen (-) instead, the permission is not granted for the group.
- 8th-10th characters: These characters indicate the read (r), write (w), and execute (x)
permissions for OTHER. The OTHER owner type consists of all other users on the system apart
from the user and the group. When one of these characters is a hyphen (-) instead, the permission is not granted for other.
<br />


<p align="center">
Change file permissions: <br/>

Example 1:
- As indicated in the output the only file grants other users write permissions is project_k.txt. We will changing the permissions of the file so that the owner type of other doesn’t have write permissions.
- To change the permissions of the file we will be using the "chmod" command.
<p align="center">
<img src="https://i.imgur.com/f33etxP.png" height="80%" width="80%" alt="File-Permissions-in-Linux"/>

- This shows how I used the command "chmod o-w project_k.txt" to change the permissions of the file so that the owner type of other doesn’t have write permissions. Then I used the commend "ls -l" to make sure that the permission of the file has been changed. 

Example 2:
- Now we will be changing the group users read permissions is project_m.txt. As you can see from the first image, project_m.txt group users only have the read permission. We will be changing the permissions of the file so that group doesn't have read permissions.
- I will be using the command "chmod g-r project_m.txt" to change the permission.

<p align="center">
<img src="https://i.imgur.com/g4rYT1Y.png" height="80%" width="80%" alt="File-Permissions-in-Linux"/>
<br/>

<p align="center">
Change file permissions on a hidden file: <br/>

- As indicated in the output the from the first image, it shows that there is one hidden file called ".project_x.txt". In the files the user has read and write permissions and group has write permissions. We will be changing the permissions of the file ".project_x.txt" so that both the user and the group can read, but not write to, the file.
- I used the command "chmod u-w,g-w,g+r .project_x.txt"

<p align="center">
<img src="https://i.imgur.com/t7nINQy.png" height="80%" width="80%" alt="File-Permissions-in-Linux"/>
<br/>

- As seen from doing "ls -la" command, the permissions have been changed. User and Group now only have read permissions.

<p align="center">
Change directory permissions: <br/>

- As indicated in the output the from the first image, there is only one directory called "drafts". It shows that user has read,write,& execute permissions and group has execute permissions.
- We will be changing permission and remove the execute permission for the group from the drafts directory.
- I will be using the command "chmod g-x drafts" to remove the execute permission for the group.

<p align="center">
<img src="https://i.imgur.com/r0oHI0v.png" height="80%" width="80%" alt="File-Permissions-in-Linux"/>

- As we can see in the drafts directory permissions, we have removed execute permission for the group. Now only the user called "researcher2" has any permissions.
<br/>



