---
marp: true
theme: gaia
class: invert
---

<!-- _class: lead -->

# Intro to Command Line Interface

---

<!--_class: lead invert-->

## CLI? Shell? Terminal?

Shell is a program that takes commands from the keyboard and gives them to the operating system to perform. In the old days, it was the only user interface available on a Unix-like system such as Linux. (It's the out most layer of the OS, thus the name)

### Different types (dialects) of shells

- Z-Shell (default for higher versions of macOS & some Linux distros)
- Bash (default for older versions of macOS & some Linux distros)
- PowerShell (default for Windows)

---

## Why use the terminal?

- Makes you much better at using your OS
  - Increase efficiency and productivity
- You just have to sometimes
  - CLI tools
  - Git
  - Package managers
- It's FUN
  - Makes you look cool
  - Makes you feel like a coder

---

## Learning Shell Commands

### Basic Navigation

- `cd`: change directory
- `pwd`: present working directory (understand where you are)
- `ls`: list files
- `rm`: delete files/directory
- `mv`: move and rename files
- `touch`: create a file
- `mkdir`: make a directory

---

- `clear`: clear the terminal screen
- `cat`: print files in your terminal

---

### Understanding Your File System

- `cd ..`: Navigate to parent directory
- `cd -`: Navigate to previous directory
- `cd ~`: Navigate to home directory
- Common directories
  - `/`: root directory
  - `/bin`: binary files
  - `/etc`: configuration files
  - `/usr/<YOUR_USERNAME>`: user home directory, YOU WILL BE HERE MOST OF THE TIME

---

### Using Flags

- `rm -r`: remove recursively (delete directory with contents)
- `rm -rf`: remove recursively and force
- `ls -a`: list all files (including hidden files)
- `--help`

---

### Greping and Searching

#### Flags with parameters

- `grep`: search for string in files
  - `grep "string" filename`: search for string in filename
  - `grep -r "string" .`: search for string in all files in current directory
- `find`: find files
  - `find . -name "filename"`: find file with name filename in current directory
  - `find . -type d`: find all directories in current directory

---

### Data piping, redirect & chaining commands

- `|`: pipe
  - `ls | grep "string"`: list all files and search for string
  - `ls | grep "string" | wc -l`: list all files, search for string, and count the number of files
- `>`: redirect
  - `echo "string" > filename`: adds string to filename. Creates file if one does not exist
  - `echo "strong" >> filename`: appends string to filename

---

- Chaining commands
  - `command 1 && command 2`: command 2 executes if command 1 was successful
  - `command 1 ; command 2`: command 2 executes no matter if command one was successful or not

---

### Make Network calls with `curl`

- `curl`: make network requests
  - `curl <URL>`: make a GET request
  - `curl -X POST -d "data" <URL>`: make a POST request with data

---

## Package Managers

### OS Package Managers

#### Installs and manages software on your machine

- MacOS
  - Homebrew
  - MacPorts
- Linux
  - Apt - Debian based distros
  - Pacman - Arch based distros

---

## Language specific package managers

### Makes managing dependencies easier

- Python
  - pip
- Java
  - Maven
- JavaScript (Node)
  - npm

---

## Beyond the Basics

### Shell Scripting

- Sourcing files
- Making files executable
- Z-Shell environment
  - Aliases
  - Functions
  - Keybinds

---

### Plugins and Tools

### [Lawrence's CLI setup](https://drive.google.com/file/d/1MbZeF0V-1JB75qxOoTH_Fk3mxsoEpRuC/view?usp=sharing)

- Z-Shell plugins
  - [oh my zsh](https://ohmyz.sh/)
  - Syntax highlighting
- Lawrence's Favorite Command line tools
  - `fzf`: command line fuzzy finder
  - `ripgrep/grep`: search for string in files
  - `fd`: better `find` command
  - `bat`: better `cat` command

---

## Exercises

1. Navigate to your home directory
2. List all the files and directories in your current directory
3. Create a directory called `test` using `mkdir`
4. Change into the `test` directory
5. Create a file called `file.txt`
6. Rename the `file.txt` file to `result.txt`

---

7. Download the text from `https://raw.githubusercontent.com/ImPrankster/tamid-tech-resources/main/cli/foundation-and-earth` to `novel.txt`
8. Search for the word `robot` (case ignored) in `novel.txt`, and output to `result.txt`
