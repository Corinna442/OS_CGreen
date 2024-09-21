## Lab 03

- Name: Corinna Green
- Email: green.442@wright.edu

## Part 1 Answers

1. `ssh` command before configuring `config` file: Host 2350
2. HostName: 98.82.48.190
3. User: ubuntu
4. IdentityFile: ~/ceg2350.pem
5. `~/.ssh/config` contents: port 22

```
Host 2350
      HostName: 98.82.48.190
      User: ubuntu
      IdentityFile: ~/ceg2350.pem
      ~/.ssh/config contents: Port 22
```

6. `ssh` command after configuring an entry in the `config` file: ssh 2350

## Part 2 Answers

1. `printenv HOME > thishouse`
   - Explanation: The "printenv" command displays the values of environment variables. In this case, the environment variable is HOME. This whole command simply displays the value of the HOME variable and outputs it to the file 'thisHouse'.
2. `cat doesnotexist 2>> hush.txt`
   - Explanation: The "2>>" command has the job of redirecting any error output and giving it to the subsequent file. In this case, that file would be the "hush.txt" file. Interestingly, there are two types of output; the 1 is represented by standard output; and the 2 is represented by error output. The operator '>>' attaches the error output to a file (hush.txt). In short, this command reads the 'doesnotexist' file and possible errors will be redirected and outputted to hush.txt.
3. `cat nums.txt | sort -n >> all_nums.txt`
   - Explanation: the 'cat num.txt' command will read out the contents of the text file. The '|' operator then takes the contents of the 'nums.txt' file and sends it as input to the next command, which would be 'sort -n'. The 'sort -n' command basically sorts the input in numerical order. The sorted output will go to 'all_nums.txt'.
4. `cat << "DONE" > here.txt`
   - Explanation: The command '<< "DONE"' takes input from the cat command to the here.txt file and gets everything until the word "DONE" is inputted.
5. `ls -lt ~ | head`
   - Explanation: The 'head' command is meant to display the first 10 lines of output. So, in this case, this whole command will list the first 10 files in the home directory (~), which will display the sorted details of these files (ls -lt).
6. `history | grep ".md"`
   - Explanation: The "grep" command will search in all of the files labeled with ".md" in the history command.

## Part 3

Verify that `roll` made it to your GitHub repository for this course and is in your `Lab03` folder.  No answers will be written here unless you would like to leave a note to the TAs

## Part 4 - Retrospective Answers

1. Where and when did it go wrong while working on your script tasks?
> I had many problems when writing the code in bash. Many of the problems included making errors because I had left something out or missed some correct spacing. Other problems I encountered were logical errors when getting my loops to run, at one point the while loop was not acting as a loop! This was challenging in that it was a new language I was learning and had to work with.
2. Was anything familiar working with a new language compared to one you are used to?
> Yes! I am used to the language java. Some of similarities were the for and while loops, if statements, and the operators like && and ||.
3. Did you write good `commit` messages that refer to what tasks were completed at each commit?  What would you improve? 
> I would say I wrote good commit messages for each commit by labeling them numbers 1-6. Although, I could improve by making a more detailed description of what I had changed each time I saved my commits.

## Part 5 Answers

1. PATH = echo $PATH
2. To set condition to `true`, I need to make sure I have/create a directory. Then, add it to ~/.profile to make it true.
3. Command(s): export PATH="$HOME/roll:$PATH"
4. PATH = /home/ubuntu/roll:/home/ubuntu/Lab03:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
   - Difference: 'roll' was added in the path.
5. Command(s): cp ~/roll ~/.profile/
6. Commands & modification explanations: chmod +x ~/profile/roll
7. Script permission breakdown
   - User
      - must be: The user/owner
      - has permissions to: run the script
   - Group
      - must be: all members of a file
      - has permissions to: execute the script
   - Other
      - has permissions to: read the script

## Extra Credit

1. Note here *what* you did to the script for the extra credit.
