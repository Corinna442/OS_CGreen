## Lab 02

- Name: Corinna Green
- Email: green.442@wright.edu

## Part 1 Answers

1. Command & steps to create an SSH key pair: First, we have to use the command "ssh-keygen -t ed25519" to generate the ssh key. Then it will give you the key fingerprint. This creates the SSH key. You will be prompted to enter a file to save this to, you can click enter and it will save it to a default file location. Then it will ask for a passphrase.
2. Steps to add public key to GitHub profile: Copy the key fingerprint and then go to your github profile. From here, go to settings, then click 'SSH and GPG keys'. Then click 'New SSH key' at the top right. Here, you will put in a title and then copy and paste the key in the bio. Now go back to your terminal and type "ssh -T git@github.com". This will test if you are in or not. If you are in, the output should look like this: "Hi [NAME]! You've successfully authenticated, but GitHub does not provide shell access". 
3. git command to clone repository: git clone git@github.com:WSU-kduncan/ceg2350f24-Corinna442.git

## Part 2 Answers

The answers for this section are to help you record what steps  
are needed to create a file locally (in your cloned repo)  
and push them (sync) with GitHub.  Only `git` commands are 
valid answers

1. git command to view the status of the repository: git status Lab02
2. git command example to add a file for tracking: git add .
3. git command to commit changes: git commit -m "Adding the Lab02"
4. git command to sync local commits with GitHub: git pull
5. git command to sync commits on GitHub to `clone`d repository: git push

## Part 3 Answers

1. `chmod u+r bubbles.txt`
    - Means: For bubbles.txt, it allows the owner/ user to read this file.
2. `chmod u=rw,g-w,o-x banana.cabana`
    - Means: For banana.cabana, it allows the owner/ user to read and write, but the group can not write and the others cannot execute in this file.
3. `chmod a=w snow.md`
    - Means: This changes the permissions by allowing all to write in snow.md. 
4. `chmod 751 program`
    - Means: This changes the permissions by allowing the user to read, write, and execute the program (7); the group to read and execute the program (5); and the others to execute the program (1).
5. `chmod -R ug+w share`
    - Means: This changes the permissions to not allow the user and group to read the file, but adds 'w' which means they can write in the file. 

## Part 4 Answers

1. Command to create new user: sudo adduser cgreen
2. Path to user's home directory: pwd cgreen /home/ubuntu/
3. Evaluate if `ubuntu` can add files to user's home directory: No- ubuntu cannot add files to the cgreen's home directory because ubuntu does not have the permissions.
4. Command to switch to user: su cgreen
5. Command(s) to go to user's home directory: cd ~
6. Evaluate if user can add files to user's home directory: Yes- 'cgreen' can add add files to their home directory. This is because ubuntu is now 'cgreen' so it has the permissions to create files in their home directory.
7. Command to switch to `ubuntu`: su ubuntu
8. Command to return to `ubuntu` home directory: cd ~

## Part 5 Answers

For each, write the command used or answer the question posed.

1. Command to create group named `crew`: sudo addgroup crew
2. Command(s) to add `ubuntu` & user to group `crew`: sudo usermod -G crew cgreen, sudo usermod -G crew ubuntu
3. Command to modify `share` to have group ownership of `crew`: sudo chgrp crew share
4. Command to switch to user: su cgreen
5. Command to add file to `share`: touch file1.txt
6. Evaluate why these steps allowed the above action: These steps allowed the cgreen user to successfully add 'file1.txt' because we gave the crew group ownership, meaning all users in it have access to the share folder within the group crew.

## Part 6 Answers

For each, write the command used or answer the question posed.

1. Command to create file using `sudo`: sudo touch sudowho.txt
2. Evaluate (in plain text) the permission of the file: The owner of this file is ubuntu and they can read and write in sudowho.txt. (-rw-rw-r-- 1)
3. Provide a method to edit the file without modifying permissions: vim sudowho.txt
4. Command(s) to modify permissions: chgrp crew sudowho.txt
                                        chown ubuntu sudowho.txt
