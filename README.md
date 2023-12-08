# File-Permissions-in-Linux

-The following code demonstrates how I used Linux commands to determine the existing
permissions set for a specific directory in the file system.

<p align="center">
Check file and directory details: <br/>
<img src="https://i.imgur.com/dSUwxLs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

- The screenshot's first line captures the command I typed, and the rest lay out what the output was. I use the ls command with the -la option to get the file content with the hidden files. The output shows that that where is a directory nameed "drafts" and a hidden file named ".project_x.txt" and a then five other project files. 

<p align="center">
Describe the permissions string: <br/>
- There are 10-character string can be deconstructed to determine who is authorized to access the
file and their specific permissions. 
The characters and what they represent are as follows:
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
<br />


