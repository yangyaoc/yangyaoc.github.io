# File permissions in Linux
## Project description
At my organization, the research team needs to update the file permissions for specific files and directories within the `projects` directory. Currently, the permissions do not  show the level of authorization that should be permitted. Checking and updating these permissions will help maintain their system secure. To achieve this task, I demonstrated the following tasks:
## Check file and directory details
The code below shows how I wrote Linux commands to exam the existing permissions set for a specific directory in the file system.

<img width="645" alt="Screenshot 2024-09-19 at 4 55 58 PM" src="https://github.com/user-attachments/assets/89ccbd44-594c-40c4-9d91-d0bc765f426f">

The first line of the screenshot shows the command I input, and the rest displays the output. The code displays all contents of the projects directory. By using `ls` command with the `-la` option, it shows a detailed listing of the file contents that also returned hidden files. The output of my command exhibits that there is one directory named `drafts`, one hidden file named `.project_x.txt`, and five other project files. The 10-character in the first column displays the permissions set on each file or directory.

## Describe the permissions string
The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:
| Character                   | Description                                 |
|----------------------------|------------------------------------------------------|
| 1st character |It is either a `d` or hyphen (`-`) and indicates the file type.  `d` is a directory. (`-`) is a regular file.|
| 2nd-4th characters |They represent the read (`r`), write (`w`), and execute (`x`) permissions for the user. When one of these characters is a hyphen (-) instead, it means this permission is not granted to the user.|
| 5th-7th characters|They represent the read (`r`), write (`w`), and execute (`x`) permissions for the group. When one of these characters is a hyphen (`-`) instead, it means that this permission is not granted for the group.|
| 8th-10th characters|They indicate the read (`r`), write (`w`), and execute (`x`) permissions for other. This owner type consists of all other users on the system apart from the user and the group.  (`-`) represents that this permission is not granted for other|

## Change file permissions
The organization decided that other shouldn't have write access to any of their files. To follow this rule, I referred to the file permissions that I previously returned. I determined `project_k.txt` must have the write access removed for other.

The code below shows how I wrote Linux commands to do this:
<img width="645" alt="Screenshot 2024-09-19 at 9 21 44 PM" src="https://github.com/user-attachments/assets/d1d9396f-9315-4059-ab52-75ad65db1c67">
