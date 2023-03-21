Terminal Cheatsheet
===================
<!-- TOC -->
* [Terminal Cheatsheet](#terminal-cheatsheet)
    * [Commands:](#commands-)
    * [Manipulating Folders and Files:](#manipulating-folders-and-files-)
    * [Flags:](#flags-)
    * [File Extensions:](#file-extensions-)
    * [Creating SSH Key for Git to GitHub:](#creating-ssh-key-for-git-to-github-)
    * [Uploading From Git to GitHub Via SSH Key:](#uploading-from-git-to-github-via-ssh-key-)
<!-- TOC -->
### Commands:

* `pwd` - print working directory, find out which folder we're currently in
* `ls` - lists all files and folders
* `mkdir` - create new folder
* `touch` - create new file
* `cd` - change directory

>Note: 
> `cd ..` returns you back one level of folder, while `cd` returns you back to the home directory

### Manipulating Folders and Files:
* `mv` - moves specified file to specified directory
> Note: `mv` can also be used to rename files with similar syntax when no directory is specified
> e.g. `mv cool_cat_photo.jpg cool_dog_photo.jpg`
* `cp` - copies specified file to specified directory
* `rm` - remove/delete specified folder or file, can force delete using flags

### Flags:
>Note: Added to the end of commands 
* `-l` - displays all details for all files details
* `-la` - displays all files and folders including hidden files
* `-r` - recursive e.g. when using rm it will recursively delete everything else in the folder selected to be deleted
* `-f` - force flag
>   **WARNING: Use of `rm -rf` cannot be reversed!!! DELETION IS FINAL AND CANNOT BE RECOVERED!!**

### File Extensions:
>Note: Added to the end of files to denote type
* .txt
* .png
* .pdf
* .jpeg
* .md

### Creating SSH Key for Git to GitHub:
* `ls -al ~/.ssh` - displays any pre-existing SSH keys on the machine
* `ssh-keygen -t ed25519 -C "your@email.com"` - creates SSH key for your local Git to connect to GitHub (cloud)
* `pbcopy < ~/.ssh/id_ed25519.pub` - copies the public SSH key to clipboard to paste into GitHub
* `ssh -T git@github.com` - tests connection of SSH key to GitHub

### Uploading From Git to GitHub Via SSH Key:
* `git init` - initialise the Git repository
* `git status` - checks the status of the Git repository and displays any modified files that are **'untracked'**
* `git add` - adds specified file to the stage
* `git commit -m"your message"` - creates a record of the files that have been staged, `-m` flag to create a descriptive message of modifications
* `git revert` - **only reverts a single specific commit**, pull the ID number of the commit from the log
* `git reset` - reverts the specified commit and all commits after it
* `git rebase` - reverses commits and removes them entirely form the history
* `git remote add origin your/url/here` - adds the location of the GitHub repository to upload to, copy path from Github when creating new repository **remembering to select SSH before copying**
* `git push` - uploads to GitHub
* `git log` - shows history of repository, hit `q` to quit the log to return to CLI
