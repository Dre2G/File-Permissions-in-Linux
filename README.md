# File-Permissions-in-Linux
<h1>File Permissions in Linux</h1>

<h2>Description</h2>
This is a project that I completed regarding File permissions in Linux. The scenerio is based on a fictional company and was completed within a shell environment.
The research team at my organization needs to update the file permissions for certain files and directories within the <em>projects</em> directory. 
The permissions do not currently reflect the level of
authorization that should be given. Checking and updating these permissions will help keep
their system secure. To complete this task, I performed the following tasks:

<br />

<h2>Scenerio</h2>

In this scenerio, I am security professional at a large organization. I mainly work with their research team. Part of my job is to ensure users 
on tis team are authorized with the appropriate permissions.

I am tasked with examining existing permissions on the file system. I will need to determine if the permissions match the authorization 
that should be given. If they do not match, I'll need to modify the permisions to authorize the appropriate users and remove 
any unauthorized access.

<p >
<h3> Check file and directory details </h3>
The following code demonstrates how I used Linux commands to determine the existing
permissions set for a specific directory in the file system.
  
<br align="center"/>
<img src="https://imgur.com/CLqvhQ0.png" height="80%" width="80%" alt="Control Categories"/>
<br />

The first line of the screenshot displays the command I entered, and the other lines display the
output. The code lists all contents of the <em>projects</em> directory. I used the <em>ls</em> command with the
<em>-la</em> option to display a detailed listing of the file contents that also returned hidden files. The
output of my command indicates that there is one directory named <em>drafts</em>, one hidden file
named <em>.project_x.txt</em>, and five other project files. The 10-character string in the first
column represents the permissions set on each file or directory.
 
<h3> Describe the permissions string </h3>

The 10-character string can be deconstructed to determine who is authorized to access the
file and their specific permissions. The characters and what they represent are as follows:
- <b>1st character</b>: This character is either a <em>d</em> or hyphen <em>(-)</em> and indicates the file type. If it’s
a <em>d</em>, it’s a directory. If it’s a hyphen <em>(-)</em>, it’s a regular file.
-   <b>2nd-4th characters</b>: These characters indicate the read <em>(r)</em>, write <em>(w)</em>, and execute <em>(x)</em>
permissions for the user. When one of these characters is a hyphen <em>(-)</em> instead, it
indicates that this permission is not granted to the user.
-   <b>5th-7th characters</b>: These characters indicate the read <em>(r)</em>, write <em>(w)</em>, and execute <em>(x)</em>
permissions for the group. When one of these characters is a hyphen <em>(-)</em> instead, it
indicates that this permission is not granted for the group.
-   <b>8th-10th characters</b>: These characters indicate the read <em>(r)</em>, write <em>(w)</em>, and execute <em>(x)</em>
permissions for other. This owner type consists of all other users on the system apart
from the user and the group. When one of these characters is a hyphen <em>(-)</em> instead,
that indicates that this permission is not granted for other.

For example, the file permissions for <em>project_t.txt</em> are <em>-rw-rw-r--</em>. Since the first
character is a hyphen <em>(-)</em>, this indicates that <em>project_t.txt</em> is a file, not a directory. The
second, fifth, and eighth characters are all <em>(r)</em>, which indicates that user, group, and other all have
read permissions. The third and sixth characters are <em>(w)</em>, which indicates that only the user and
group have write permissions. No one has execute permissions for <em>project_t.txt</em>.

<br />

<h3>Change file permissions</h3>

The organization determined that other shouldn't have write access to any of their files. To
comply with this, I referred to the file permissions that I previously returned. I determined
<em>project_k.txt</em> must have the write access removed for other.

The following code demonstrates how I used Linux commands to do this:

<br/>
<img src="https://imgur.com/uEcfgI7.png" height="80%" width="80%" alt="Control Categories"/>
<br />

The first two lines of the screenshot display the commands I entered, and the other lines
display the output of the second command. The <em>chmod</em> command changes the permissions on
files and directories. The first argument indicates what permissions should be changed, and
the second argument specifies the file or directory. In this example, I removed write
permissions from other for the <em>project_k.txt</em> file. After this, I used <em>ls -la</em> to review the
updates I made.


<br />

<h3>Changing file permissions on hidden file</h3>

The research team at my organization recently archived project_x.txt. They do not want
anyone to have write access to this project, but the user and group should have read access.

The following code demonstrates how I used Linux commands to change the permissions:

<br/>
<img src="https://imgur.com/OUoRCU8.png" height="80%" width="80%" alt="Compliance Checklist choices"/>
<br />

The first two lines of the screenshot display the commands I entered, and the other lines
display the output of the second command. I know <em>.project_x.txt</em> is a hidden file because
it starts with a period <em>(.)</em>. In this example, I removed write permissions from the user and
group, and added read permissions to the group. I removed write permissions from the user
with <em>u-w</em>. Then, I removed write permissions from the group with <em>g-w</em>, and added read
permissions to the group with <em>g+r</em>.


<br />

<h3>Change directory permissions</h3>

My organization only wants the <em>researcher2</em> user to have access to the <em>drafts</em> directory
and its contents. This means that no one other than <em>researcher2</em> should have execute
permissions.

The following code demonstrates how I used Linux commands to change the permissions:


<br/>
<img src="https://imgur.com/VGs0H0M.png" height="80%" width="80%" alt="Risk Assessment"/>
<br />

The first two lines of the screenshot display the commands I entered, and the other lines
display the output of the second command. I previously determined that the group had
execute permissions, so I used the <em>chmod</em> command to remove them. The <em>researcher2</em> user
already had execute permissions, so they did not need to be added.

<br />

<h3>Summary</h3>

I changed multiple permissions to match the level of authorization my organization wanted for
files and directories in the <em>projects</em> directory. The first step in this was using <em>ls -la</em> to
check the permissions for the directory. This informed my decisions in the following steps. I
then used the <em>chmod</em> command multiple times to change the permissions on files and
directories
