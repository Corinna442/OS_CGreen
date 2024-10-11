## Lab 06

- Name: Corinna Green
- Email: green.442@wright.edu

## Part 2 - Retrospective

1. Getopts is like a switch statement on steriods. It defines which options the script will accept, such as the ones we used like h, f, r, and /?. The user will pick from these cases (options) in order to complete their action. 
2. I got stuck on the error: `mv: cannot stat '': No such file or directory`. I basically had the file name be called fileName and accidentally forgot to put an uppercase N for the rest of the variables (which were mistakenly called filename).
3. I would include the possibility of making more functions for the loops and the error checking.

## Part 3 - namechange Usage Guide

Usage: namechange -f find -r replace "string to modify"

 `-f` The text to find in the filename

 `-r` The replacement text for the new filename

### What it is

This script finds and replaces file names using getopts and sed. If you need help, it will print out a usage guide to tell you what commands/options using `-h`. It will also display error messages if you put in a nonexistant filename or command. 

### How to run it

If someone wanted to downloaded your script, what steps would they take to have their own copy that they could run
1. First, make a file named namechange using vim, then copy and paste my script.
2. Create error files for this script to change such as `pic.jgp` or `foo.txt`.
3. Run it using this format: `bash ./namechange -f old -r new old.txt`

### Examples

```
Example 1: Run it using this format: `./namechange -f old -r new old.txt`
This will chnage `old.txt` to `new.txt`
Example 2: change `foo.txt` to `foobar.txt`: `./namechange -f foo -r foobar foo.txt`

```

## Bulk Name Changer Usage Guide - Remove if not doing extra credit

Examples of script usage and output. This should be enough info that  
you can hand this and the script to someone not in this course and they  
would be able to understand what your script does and how to use it.

Use good markdown so that this documentation it is pretty and clean on GitHub.
