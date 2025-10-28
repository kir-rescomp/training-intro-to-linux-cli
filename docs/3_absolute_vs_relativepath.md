# 3. Absolute vs Relative Paths


The `cd` command takes an argument which is a directory name. Directories can be specified using either a _relative_ path or a
full _absolute_ path. The directories on the computer are arranged into a hierarchy. The full path tells you where a directory is in that
hierarchy. Navigate to the home directory, then enter the `pwd` command.


!!! terminal "code"

    ```bash
    $ cd
    $ pwd
    ```

    You will see:

    ```output
    /users/group/user
    ```

This is the full name of your home directory. This tells you that you
are in a directory called `training`, which sits inside a directory called
`home` which sits inside the very top directory in the hierarchy. The
very top of the hierarchy is a directory called `/` which is usually
referred to as the _root directory_. So, to summarize: `training` is a
directory in `home` which is a directory in `/`. More on `root` and
`home` in the next section.

!!! terminal-2 "Now enter the following command:"

    ```bash
    $ cd /users/group/user/shell_data/.hidden
    ```

    This jumps forward multiple levels to the `.hidden` directory.
    Now go back to the home directory.

    ```bash
    $ cd
    ```

You can also navigate to the `.hidden` directory using:

!!! terminal "code"

    ```bash
    $ cd ~/shell_data/.hidden
    ```

These two commands have the same effect, they both take us to the `.hidden` directory.
The first uses the absolute path, giving the full address from the home directory. The
second uses a relative path, giving only the address from the working directory. A full
path always starts with a `/`. A relative path does not.

A relative path is like getting directions from someone on the street. They tell you to
"go right at the stop sign, and then turn left on Main Street". That works great if
you're standing there together, but not so well if you're trying to tell someone how to
get there from another country. A full path is like GPS coordinates. It tells you exactly
where something is no matter where you are right now.

You can usually use either a full path or a relative path depending on what is most convenient.
If we are in the home directory, it is more convenient to enter the full path.
If we are in the working directory, it is more convenient to enter the relative path
since it involves less typing.

Over time, it will become easier for you to keep a mental note of the
structure of the directories that you are using and how to quickly
navigate amongst them.

# Relative path resolution

!!! dumbbell "Using the filesystem diagram below, if `pwd` displays `/Users/thing`," what will `ls ../backup` display?"

    1. `../backup: No such file or directory`
    2. `2012-12-01 2013-01-08 2013-01-27`
    3. `2012-12-01/ 2013-01-08/ 2013-01-27/`
    4. `original pnas_final pnas_sub`

    ![](images/filesystem-challenge.svg){alt='File System for Challenge Questions'}


    ??? success "Solution"

        1. No: there _is_ a directory `backup` in `/Users`.
        2. No: this is the content of `Users/thing/backup`,
           but with `..` we asked for one level further up.
        3. No: see previous explanation.
           Also, we did not specify `-F` to display `/` at the end of the directory names.
        4. Yes: `../backup` refers to `/Users/backup`.


### Navigational Shortcuts

The root directory is the highest level directory in your file
system and contains files that are important for your computer
to perform its daily work. While you will be using the root (`/`)
at the beginning of your absolute paths, it is important that you
avoid working with data in these higher-level directories, as
your commands can permanently alter files that the operating
system needs to function. In many cases, trying to run commands
in `root` directories will require special permissions which are
not discussed here, so it's best to avoid them and work within your
home directory. Dealing with the `home` directory is very common.
The tilde character, `~`, is a shortcut for your home directory.
In our case, the `root` directory is **two** levels above our
`home` directory, so `cd` or `cd ~` will take you to
`/home/<username>` and `cd /` will take you to `/`. Navigate to the
`shell_data` directory:

!!! terminal "code"

    ```bash
    $ cd
    $ cd ~/shell_data
    ```

    Then enter the command:

    ```bash
    $ ls ~
    ```

    ```output
    shell_data
    ```

This prints the contents of your home directory, without you needing to
type the full path.

!!! quote ""

    The commands `cd`, and `cd ~` are very useful for quickly navigating back to your home directory. We will be using the `~` character in later lessons to specify our home directory.

!!! graduation-cap "Summary"

    - The `/`, `~`, and `..` characters represent important navigational shortcuts.
    - Hidden files and directories start with `.` and can be viewed using `ls -a`.
    - Relative paths specify a location starting from the current location, while absolute paths specify a location from the root of the file system.
