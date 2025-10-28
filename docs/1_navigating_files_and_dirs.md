# 2, Navigating Files and Directories

!!! clipboard-list "Episode objectives"

    - Navigate your file system using the command line.
    - Access and read help files for `bash` programs and use help files to identify useful command options.
    - Demonstrate the use of tab completion, and explain its advantages.

## How to access the Shell

On a Mac or Linux machine, you can access a shell through a program called "Terminal", which is already available on your computer. The Terminal is a window into which we will type commands. If you're using Windows, you'll need to download a separate program to access the shell.

To save time, we are going to be working on a remote server where all the necessary data and software available. When we say a 'remote server', we are talking about a computer that is not the one you are working on right now.

## Navigating File system 

The part of the operating system that manages files and directories is called the file system. It organizes our data into files, which hold information, and directories (also called "folders"), which hold files or other directories.

Several commands are frequently used to create, inspect, rename, and delete files and directories.\

!!! terminal "code"

    ```bash
    $ 
    ```
The dollar sign is a **prompt**, which shows us that the shell is waiting for input;
your shell may use a different character as a prompt and may add information before
the prompt. When typing commands, either from these lessons or from other sources,
do not type the prompt, only the commands that follow it.

Let's find out where we are by running a command called `pwd` (which stands for "print working directory"). At any moment, our **current working directory**
is our current default directory, i.e. the directory that the computer assumes we want to run commands in, unless we explicitly specify something else.
Here, the computer's response is `/users/group/user`, which is the top level directory within BMRC:

!!! terminal "code"

    ```bash
    $ pwd
    ```

    ```output
    /users/group/user
    ```
Let's look at how our file system is organized. We can see what files and subdirectories are in this directory by running `ls`,
which stands for "listing":

!!! terminal "code"

    ```bash
    $ ls
    ```

    ```output
    shell_data
    ```

`ls` prints the names of the files and directories in the current directory in alphabetical order, arranged neatly into columns. We'll be working within the `shell_data` subdirectory, 
and creating new subdirectories, throughout this workshop.

The command to change locations in our file system is `cd`, followed by a
directory name to change our working directory. `cd` stands for "change directory".

Let's say we want to navigate to the `shell_data` directory we saw above. We can
use the following command to get there:


!!! terminal "code"

    ```bash
    cd shell_data
    ```

    and take a look

    ```bash
    $ ls
    ```

    ```output
    sra_metadata  untrimmed_fastq
    ```
We can make the `ls` output more comprehensible by using the **flag** `-F`,
which tells `ls` to add a trailing `/` to the names of directories:

!!! terminal "code"

    ```bash
    $ ls -F
    ```

    ```output
    sra_metadata/  untrimmed_fastq/
    ```

!!! circle-info "what is `/`"

    Anything with a `/` after it is a directory. Things with a "\*" after them are programs. If
    there are no decorations, it's a file.


!!! circle-info "`ls` has lots of other options. To find out what they are, we can type:"

    ```bash
    $ man ls
    ```

    `man` (short for manual) displays detailed documentation (also referred as man page or man file)
    for `bash` commands. It is a powerful resource to explore `bash` commands, understand
    their usage and flags. Some manual files are very long. You can scroll through the
    file using your keyboard's down arrow or use the <kbd>Space</kbd> key to go forward one page
    and the <kbd>b</kbd> key to go backwards one page. When you are done reading, hit <kbd>q</kbd>
    to quit.

!!! magnifying-glass "Busy looking terminal ? time to 🆑"
    
    Type the word `clear` into the terminal and press the `Enter` key.

    !!! terminal "code"

        ```bash
        $ clear
        ```

    This will scroll your screen down to give you a fresh screen and will make it easier to read.
    You haven't lost any of the information on your screen. If you scroll up, you can see everything that has been output to your screen
    up until this point.



    !!! tip "Hot-key combinations are shortcuts for performing common commands."

        The hot-key combination for clearing the console is `Ctrl+L`. Feel free to try it and see for yourself.
