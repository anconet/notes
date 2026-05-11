# Linux Basics

```bash

# Current directory
pwd

# What files are in the directory
ls
ls -la # more details
ls -lat # more details in time order

# Change directories
cd
cd ~ # Change to my home directory
cd .. # Up one directory
cd / # To the top of the file system

# Create a directory
mkdir <newDirectoryName>

# Remove things
rm file.txt
rm -f file.txt # Force the removal
rm -rf directory # Recursively remove the directory and all of the contents

# Create a file
touch file.txt # creates an empty file
vim file.txt # create and edit a new fime

# See what's in a file
cat file.txt # dumps the contents of the file to the terminal
less file.txt # Displays the file
    q to quit
    /<string> to search
        n to search the next occurence forward
        N to search backwards
    h navigate left
    j navigate up
    k nvaigate down
    l navigate right

# getting help
<command> -h # older
<command> --help # newer
man <command> # loads the manual page for the command. Navigate like the ***less*** command
```
Using `vim`
```bash
vim file.txt # creates the new file

# In command mode
i to start inserting
shift-A start inserting at the end of the line
/<string> to search
    n next
    N previous
:q quit without saving
:qw quit with saving

# In INSERT mode
Move and type freely
Esc to exit insert mode
```