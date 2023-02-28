# [Introduction to the Command Line](https://launchschool.com/books/command_line/read/command_line_interface)

## [Introduction](https://launchschool.com/books/command_line/read/introduction)

- The CLI
- 'Linux operating system is the most commonly used for servers' Mac OS X and Unix are very similar. Windows is a bit different.
- This book assumes you're using a bash shell. More recent Macs use Zsh. (Bash prompts with a `$`, Zsh with a `%`).
- The prompt. Changes when you are logged in as (all-powerful) root user. Then it is `#`.
- To show whether you're using Bash or Zsh, run `echo $SHELL` and the output will be something like `usr/bin/bash`.
```ruby
echo "Hello World"
# => "Hello World"
```
Why use the CLI? 

 - Understand the commands that tutorials tell you to use. (install software, see under the hood for computer commands and processes)
 - Have power of precision over the computer. (monitor your computer and its resources, diagnose software issues)

## [Preparations](https://launchschool.com/books/command_line/read/preparations)

 - Setting up a virtual server on your computer.

## [The CLI](https://launchschool.com/books/command_line/read/command_line_interface)

 - An interface is:
   -  #1 A display of information about what the computer is doing. (DISPLAY)
   -  #2 A method for telling the computer what to do. (INPUT)
 - The Display:
   - Most computers use a program like 'Terminal'
   - The components of the CLI display are:
     - The prompt
     - the cursor
     - the input
     - the output
  - The input:
    - Will always take the format: `[command][arguments]` 
  
  - The most common use of the command line is what's called 'system administration', which is just managing computers and servers. THis includes installing and configuring software, monitoring comnputer resources, setting up web-servers and automating processes. These include common tasks such as:
    - Restart servers
    - Rename hundreds/thousands of fiules according to a prescribed pattern
    - Manage system logs
    - Sety up scheduled tasks (cron jobs)
    - Debug server issues
    - Monkey patch code on a server
    - query data
    - set up databases and servers 

- The `/` is the root directory

## [Files, Directories and the Command Line](https://launchschool.com/books/command_line/read/files_directories_executables)
### Linux/Unix File System
  - `/` - root directory
  - `.` current directory
  - `..` directory one level up
  - `../..` directory 2 levels up ie `/home/ubuntu/../.././home/ubuntu/`
  - `~` home directory
  - `*` splat operator, represents 'any character'.
 ### Navigating
 
 ### Executables
 
 Each command is in fact a file. Files that can be used as commands are called 'executables'.
   - They have special characters at the beginning to tell the computer how to execute them.
   - They have scripts or machine language as their content.
   - They have the executable permission. 

Run executables by typing its path and then your arguments: `/bin/echo "Hello World"`

## [The environment](https://launchschool.com/books/command_line/read/environment)

### Environment variables
 - `cd $HOME` works as `cd /home/ubuntu` because `HOME` is a variable.
 - When you log into the command line a set of variables are automatically set.
### How to change your command line environment
 ```ruby
SOMETHING="some value"
echo $SOMETHING
# => some value
```
 - To change your prompt:

```ruby
$ PS1="(testprompt)> "
(testprompt)>
```

- Then there's a section on creating a `.bashrc` file and `.bash_profile` file.
- Then there's a section on permanently changing your bash prompt.
- A note about how single v double quotes interpolates differently.

### [$PATH and Executables](https://launchschool.com/books/command_line/read/environment#path)

- The `PATH` variables gives context that the Command Line needs to figure out which file to execute. It determines which directories are searched when a command is entered.
- `PATH` is an ordered, colon-delimited, list of directories that contains executables.
- The order of the directories is first-found-first-execute.
- If you use `/`,`.`, or `~` before a command the command line will interpret that as an actual path to a file and not use `PATH`.
- You can add `PATH` to make them available without having to memorise their paths.
- Modifications to `PATH` will not be permanent. Permanent changes should be done in an environment file.

```ruby
$PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games
```
- * `bin` is short for binary
- `which [executable file]` is used here to see where a command is to be found.
- The path lookup rules for all commands relies heavily on managing the `$PATH` environment carefully.

## [Permissions](https://launchschool.com/books/command_line/read/permissions)

- Ownership
  - user
  - group
  - other 
- Access
  - read (`r`)
  - write (`w`)
  - execute (`x`)

- VIP lounge at airport analogy

### [Interpreting permissions](https://launchschool.com/books/command_line/read/permissions#interpretingpermissions)
- How to read permissions:
```
# +-------- Directory or not
# |  +------- User Read, Write, Execute
# |  |   +------- Group Read, Write, Execute
# |  |   |   +----- Other Read, Write, Execute
# |  |   |   |   +--- The name of the user
# |  |   |   |   |     +--- The name of the group
# |  |   |   |   |     |
# d|rwx|rwx|rwx user group
```
### [Setting permissions](https://launchschool.com/books/command_line/read/permissions#settingpermissions)

- One can set permissions with octal numbers:
```
$ chmod 777 test.sh

$ ls -l test.sh
-rwxrwxrwx  1 bob admin 0B Jul 15 15:24 test.sh

$ chmod 000 test.sh

$ ls -l test.sh
----------  1 bob admin 0B Jul 15 15:24 test.sh

$ chmod 754 test.sh

$ ls -l test.sh
-rwxr-xr--  1 bob admin 0B Jul 15 15:24 test.sh
```
- 
### [Users and Groups](https://launchschool.com/books/command_line/read/permissions#usersandgroups)

- All files and directories in Linux/Unix are assigned to a user and a group.
- Users can belong to multiple groups, which will grant it access-types assigned to that group.
- Groups can have multiple users.
- Use the `groups` command to see if your user is part of a certain group:
```
groups
# => staff everyone localaccounts _appserverusr admin _appserveradm _lpadmin com.apple.sharepoint.group.1 _appstore _lpoperator _developer _analyticsusers com.apple.access_ftp com.apple.access_screensharing com.apple.access_ssh com.apple.access_remote_ae
```

### [Root user and Sudo](https://launchschool.com/books/command_line/read/permissions#rootuserandsudo)

- 'Root' is the super-user (in Linux/Unix). In the airport analogy it is god. So only log in as root when strictly necessary.
- Switch to root user with the command: `su -` and then password.
- Even root cannot execute a file with no execute permission.
- `sudo` is like 'super-user do' and is a safer way of borrowing root user's power for a single command.
## My CLI vocab
(I'm only noting those that I haven't remembered and made part of my daily coding usage)

[Some common commands](https://launchschool.com/books/command_line/read/command_line_interface#commoncommands)

- `echo` - sends text to the CLI's output.
- `tar` - an archival command that can archive, compress and extract files.
 
 ```ruby
 $ tar -c -z -f ./archive.tgz ./files-to-archive/
 ```
- `man [command]` - prints out the manual of a command
- `cat` - display contents of a file
- `more` - prints contents, one screens-worth at a time. (quit with `q`).
- `less` - when you need to navigate backwar and forward in a file with up and down arrows (quit with `q`)
- `head`
- `tail`
- `ls -lah` - this flag prints directory-contents with information about the files.
- `mv example1.txt tmp` - here `tmp` is a different directory. This is how you move a file to another directory.
-  `cp example2.txt tmp` - works for `cp` also.
- `rm -r [folder name]` - deletes folder and all its files / subdirectories
- `cd` without args take you to home directory.
- `ls /*ot` - lists all files ending in 'ot'.
- 'tree' - prints a visual representation of current directory and children.
- `ctrl + C` - terminates process.
- `which` - tells you where a command is stored. `which touch`
- `chmod` - change files permissions ie. `chmod +w sample.txt` to add write access. More examples:
``` 
$ ls -lah test.txt
-rwxr--r--  1 bob  staff  1GB Jul 14 15:24 test.txt

$ # Remove write access for user
$ chmod u-w test.txt
$ ls -lah test.txt
-r-xr--r--  1 bob  staff  1GB Jul 14 15:24 test.txt

$ # Add execute access for group
$ chmod g+x test.txt
$ ls -lah test.txt
-r-xr-xr--  1 bob  staff  1GB Jul 14 15:24 test.txt
```
- 
