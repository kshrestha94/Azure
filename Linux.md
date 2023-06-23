## Linux Markdown

```
Starting your virtual machine VM
1. open Azure and click on the tab Virtual Machine and select your VM created. press start and ok. status should state running when working.
2. click connect and enter public key path:    
3. copy onto clipboard the run example command   
4. to exit VM hit command exit and stop VM on Azure
 
what is Linux and why are we using it ?

An operating system like windows or mac os.It is open source that uses a command line interface. Flexible, cheaper, robust, scales well to perfom different tasks. You can run linux on small devices like rasbery pie. Popular for work desktop use and applications and used in devops. You can make you more employable for the role.clone of a unix OS for large main frame. 

what is Bash?
Bourne Again Shell (Bash) improved version used in unix. unix is a commmand drivin OS. 
Linux also has a shell. 

```
## History of commands used on GITBASH!
```

1.	ls (list of all directories)
2.	ls -a (shows all files and directories, including hidden files) 
3.	touch test.txt (Create blank/empty files)
4.	ls -l (detail of files in folder)
5.	clear (clear screen)
6.	uname (Linux command to get basic information about the OS)
7.	exit (switch off from VM on GITBASH)
8.	history (history of all commands)
9.	cd (Linux command to navigate through directories)
10.	pwd (print current working directory)
11.	curl (use url)
12.	cp cat.txt (Similar usage as mv but for copying files in Linux)
13.	mkdir funny-stuff (Command used to create directories in Linux)
14.	file Cat.jpg
15.	mkdir my pictures
16.	rm -r my (Delete files or directories)
17.	rm -r pictures
18.	mkdir "my pictures" (create a new file directory with the file name ("my pictures"))
19.	cat chicken-joke,txt (Display file contents on the terminal)
20.	head -2 chicken-joke,txt (Return the specified number of lines from the top)
21.	tail -2 chicken-joke,txt (Return the specified number of lines from the bottom)
22.	history (this command allows you to see a list of all commands used in the terminal)
23.	ssh (Secure Shell command in Linux)
```

## Task 2.8 

```
Why is managing file ownership important?
Ensures data security, accountability, collaboration, system administration, and compliance with various standards.

What is the command to view file ownership?
The command syntax to view file owenership is ls-l
To view file ownership of a specific file ls -l <file name>

What permissions are set when a user creates a file or directory? Who does file or directory belong to?
The default permissions and ownership of a file/directory is determined by the umask value and the user's account settings at the time of creation. The file or directory is owned by the user who created it; linked to the user account that was used to create the file or directory.

Why does the owner, by default, not receive X permissions when they create a file?
To improve security and prevent accidental execution of files. The file owner can manually grant execute permissions to themselves or others using the command chmod. This allows control over which files should be executed as programs, preventing accidental execution and security vulnerabilities.

What command is used to change the owner of a file or directory?
The command  "chown" allows you to change the ownership of a file or directory, granting ownership to a specific user or group. 
General syntax: chown new_owner <file_or_directory>

```
## 2.8b task
```
Does being the owner of a file mean you have full permissions on that file? Explain.
Ownership determines who owns the file and who has certain administrative privileges, such as changing permissions, changing ownership, or deleting the file. 
Permissions define the access rights granted to the owner, members of the file's group, and others in terms of reading (r), writing (w), and executing (x) the file. Permissions can be set independently for each category of users.

If you give permissions to the User entity, what does this mean?

There are three basic permissions given to the user entity. 
read 
write 
execute 

When the Read permission is granted, the owner can view the contents of the file. 
Write permission, the owner can modify the file. This includes editing the content of the file, appending new data, or deleting its contents. 
Execute permission allows the owner to execute the file as a program or script if it is an executable file. Execute permission is typically used for scripts, binaries, or programs. 
If the User entity lacks execute permission, they cannot execute the file as a program, even if they have ownership.



If you give permissions to the Group entity, what does this mean?

Read (r) permission: If granted to the Group entity, all users who are part of that group can read the contents of the file, view its attributes, and list the file's directory contents.
Write (w) permission: With write permission, the group members can modify the file, append to it, or delete its contents. They can also rename or move the file within the same directory.
Execute (x) permission: Execute permission allows the group members to execute the file if it is a program, script, or executable file. They can run the file as a command or script, triggering its functionality.



If you give permissions to the Other entity, what does this mean?

Read (r) permission: If granted to the Other entity, all users who are not the owner or part of the group associated with the file can read the contents of the file, view its attributes, and list the file's directory contents.
Write (w) permission: With write permission, the other users can modify the file, append to it, or delete its contents. They can also rename or move the file within the same directory.
Execute (x) permission: Execute permission allows the other users to execute the file if it is a program, script, or executable file. They can run the file as a command or script, triggering its functionality.

You give the following permissions to a file: User permissions are read-only, Group permissions are read and write, Other permissions are read, write and execute. You are logged in as the user which is owner of the file. What permissions will you have on this file? Explain.
As the owner of the file, you will have read-only access to the file based on the User entity permissions. If you want to modify the file or execute it as a program, you would need to change the permissions accordingly, granting yourself the necessary access rights.


Here is one line from the ls -l. Work everything you can about permissions on this file or directory.

The owner (User entity) has read, write, and execute permissions (rwx).
The group (Group entity) has read and execute permissions (r-x).
Others (Other entity) have read-only permissions (r--).

```

## Task 2c 

```
What numeric values are assigned to each permission?
Read (r) permission: Assigned a value of 4.
Write (w) permission: Assigned a value of 2.
Execute (x) permission: Assigned a value of 1.

What can you with the values assign read + write permissions?
read + write permissions ("6") provide the ability to read and modify the contents of a file or directory. It allows you to view the file's data, make changes to it, create new files, rename/move the file, and delete it if desired. 

What value would assign read, write and execute permissions?
4 (Read) + 2 (Write) + 1 (Execute) = 7
assigning the value "7" to the permissions means read, write, and execute access is granted, allowing the user or entity to have full control over the file or directory, including viewing, modifying, and executing its contents

What value would assign read and execute permissions?
4 (Read) + 1 (Execute) = 5
assigning the value "5" to the permissions means read and execute access is granted, allowing the user or entity to view the contents and execute the file or directory as a program or script.

Often, a file or directory's mode/permissions are represented by 3 numbers. What do you think 644 would mean?
the mode "644" means the following permissions:
The User (Owner) has read and write permissions (6).
The Group has read-only permission (4).
Others (everyone else) have read-only permission (4).
```

## task 2d
```
What command changes file permissions?
chmod command 

To change permissions on a file what must the end user be? (2 answers)
end user must either be the owner of the file or have superuser (root) access.

Give examples of some different ways/syntaxes to set permissions on a new file (named testfile.txt) to:

Set User to read, Group to read + write + execute, and Other to read and write only
chmod u+r,g=rwx,o=rw testfile.txt

Add execute permissions (to all entities)
chmod +x testfile.txt

Take write permissions away from Group
chmod g-w testfile.txt

Use numeric values to give read + write access to User, read access to Group, and no access to Other.
chmod 640 testfile.txt

user 
group
other








```