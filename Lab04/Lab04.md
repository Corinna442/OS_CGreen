## Lab 04

- Name: Corinna Green
- Email: green.442@wright.edu

## Part 1 - Task Tracker

Verify that `tt` made it to your GitHub repository for this course and is in your `Lab04` folder.  No answers will be written here unless you would like to leave a note to the TAs

## Part 2 - Sample Runs

### User Guide

Task Tracker User Guide:
Usage: ./tt [add, complete, view, clear, help] [task description]
Here are the actions:
add : Adds a task. Needs a task description.
complete : Will mark a task as complete. This also needs a task description
view : View all tasks
clear : Clears all tasks
help : Displays this user guide

### Sample runs

Example of using `add` task
```
*Add Task*
* Command: 'tt add \"<taskDescription>\"'
 \`\`\`
   $ tt add \"Do the laundry\"
   Task added: Do the laundry
   \`\`\`
```

Example of using `complete` task
```
*Complete a Task*
   * Command: `tt complete \"<taskDescription>\"`
   * Example:
   \`\`\`
   $ tt complete \"Do the laundry\"
   Task completed: Do the laundry
   \`\`\`
```

Example of using `view` tasks
```
*View all Tasks*
   * Command: `tt view`
   * Example:
   \`\`\`
   $ tt view
   1. Do the laundry
   2. Take out trash
   \`\`\`
```

Example of using `clear` tasks
```
*Clear all Tasks*
   * Command: `tt clear`
   * Example:
   \`\`\`
   $ tt clear
   Do you want to remove all tasks? (enter y / n):
   All tasks cleared.
   \`\`\`
```

Example of using `help`
```
*Help*
   * Command: `tt help`
   * This displays the user guide.
```

## Part 5 - PATH for all

- Chosen PATH directory: /usr/local/bin
- Link preference (hard or symbolic): symbolic
   - Justification of preference for this use case: We use a symbolic link in this case because we use it as a path to the specific file.
- Command to create link: sudo ln -s /home/ubuntu/OS_CGreen/Lab04/tt /usr/local/bin/tt
- Notes about permissions modified: chmod +x /home/ubuntu/OS_CGreen/Lab04/tt
- How you tested that you can run `tt` from anywhere on filesystem: tt
- How you tested that other users can run `tt`: I switched to another user using sudo and su and ran the script.

## Extra Credit

Note here *what* you did to the script for the extra credit and provide additional demonstrations.

- I made functions for add, complete, view, clear, and help.
- I added the action 'super-show' so that every user could write tasks and store them in .tasks.
