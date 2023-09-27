## High Level Concepts

### Why use the terminal?

- Makes you much better at using your OS
  - More configuration
  - Increase efficiency and productivity
- You just have to sometimes
  - CLI tools
  - Git
  - Package managers
- It's fun
  - Makes you look cool
  - Makes you feel like a coder

### Types of shells

- Z-Shell
- Bash
- Powershell

## Learning Shell Commands

### Basic Navigation

- `cd`: change directory
- `cd ~`: Navigate to your home directory
- `cd /`: Navigate to your root directory
- `pwd`: present working directory (understand where you are)
- `ls`: list files
- `rm`: delete files/directory
- `mv`: move and rename files
- `touch`: create a file
- `mkdir`: make a directory
- `rmdir`: remove a directory

### Understanding Your File System

- `cd ..`: Navigate to parent directory
- `cd -`: Navigate to previous directory
- `echo`: printing variable
- Declaring environment variables
  - Declare and asign value to variable with `VAR="string"` (spaces matter)
  - Print value of variable with `echo $VAR`
- `*`: All the files in your pwd
- String matching
  - `*string*`: all filenames that contain string
  - `*string`: all filenames that end with string
  - `string*`: all filenames that start with string

### Doing More with your Terminal

- `clear`: clear the terminal screen
- `cat`: print files in your terminal
- `echo "string" > filename`: adds string to filename. Creates file if one does not exist
- `echo "strong" >> filename`: appends string to filename
- Chaining commands
  - `command 1 && command 2`: command 2 executes if command 1 was successful
  - `command 1 ; command 2`: command 2 executes no matter if command one was successful or not

### Using Flags

- `rm -r`: remove recursively (delete directory with contents)
- `rm -rf`: remove recursively and force
- `ls -a`: list all files (including hidden files)
- `--help`
- `man`: read the manual page for the commands

## Package Managers & Additional Tools

### Common Package Managers

- MacOS
  - Homebrew
  - MacPorts
- Linux
  - Apt - Debian based distros
  - Pacman - Arch based distros

## Beyond the Basics

### Shell Scripting

- Sourcing files
- Making files executable
- Z-Shell environment
  - Aliases
  - Functions
  - Keybinds

### Plugins and Tools

- Z-Shell plugins
  - [oh my zsh](https://ohmyz.sh/)
  - Syntax highlighting
  - AI autocomplete
- Lawrence's Favorite Command line tools
  - `fzf`: command line fuzzy finder
  - `ripgrep/grep`: search for string in files
  - `fd`: better `find` command
  - `exa`: better `ls` and `tree` command
  - `bat`: better `cat` command

### Portable development environment

- Intermediate to advanced configurations

## Exercises

### Exercise 1

1. Navigate to your home directory
2. List all the files and directories in your current directory
3. Create a directory called `test` using
4. Change into the `test` directory
5. Create a file called `file.txt`
6. List the contents of the test directory
7. Rename the `file.txt` file to `newfile.txt`
8. List the contents of the test directory again
9. Change back to the parent directory
10. Remove the `test` directory and all its contents

### Exercise 2

1. Navigate to your home directory
2. Create a directory called `temp`
3. Create two files, `temp1.txt`, `temp2.txt`
4. Add the string `"Hello Temp 1!"` to `temp1.txt` (without opening VScode)
5. Add the string `"Hello Temp 2!"` to `temp2.txt`
6. Append the string `"New Line"` to `temp2.txt`
7. Combine the contents of `temp1` and `temp2` and add that to a file called `test`
8. Delete all contents of `temp` directory and all the files in it (using one command)
