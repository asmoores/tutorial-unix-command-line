# Useful Unix/Linux Commands

## Documentation and Help

### man

The `man` command in Linux and Unix-like systems is used to display the manual pages (or man pages) for various commands, system calls, library functions, and configuration files. The manual pages provide detailed documentation and instructions on how to use and understand various aspects of the system.

Here are some key points about the `man` command:

1. Command Syntax: The basic syntax for using the `man` command is as follows:

   ```shell
   man [section] command_name
   ```

   - `section` refers to the specific section of the manual to search in. If not specified, `man` will display the first available manual page it finds for the command.
   - `command_name` is the name of the command or topic you want to search for in the manual.

2. Manual Sections: The manual is divided into several numbered sections, each covering a specific topic. The most common sections are:

   - Section 1: Executable programs or commands.
   - Section 2: System calls (functions provided by the kernel).
   - Section 3: Library functions (functions provided by libraries).
   - Section 4: Special files (devices and drivers).
   - Section 5: File formats and conventions.
   - Section 6: Games.
   - Section 7: Miscellaneous (including macro packages and conventions).
   - Section 8: System administration commands.

3. Navigating the Manual Pages: Once you open a manual page using `man`, you can navigate through it using keyboard commands. Common navigation commands include:

   - Arrow keys or Page Up/Page Down: Scroll through the manual page.
   - Home/End: Go to the beginning or end of the page.
   - /pattern: Search for a specific pattern within the manual page.
   - q: Quit and exit the manual viewer.

4. Multiple Matches: If multiple manual pages match your search term, you can navigate through the available options using the `n` (next) and `p` (previous) commands.

5. Supplementary Information: Some manual pages provide additional information in the "SEE ALSO" section, which lists related commands or topics that you may find useful.

The `man` command is a valuable resource for learning about commands, understanding their usage, and exploring system documentation. By using `man`, you can access comprehensive and detailed information about various aspects of the Linux or Unix-like system, helping you become more proficient in using the available tools and understanding their functionalities.

### which

The `which` command is not a built-in command in Unix-like shells, but it is a commonly used command-line utility for locating the executable file associated with a given command. It is available as a separate executable program in Unix-like systems.

The general syntax of the `which` command is as follows:

```shell
which [options] command
```

Here are some key points about the `which` command:

- **Locating Executable Files**: The primary purpose of `which` is to locate the executable file associated with a command. When you provide a command as an argument to `which`, it searches the directories listed in the `PATH` environment variable to find the executable file corresponding to that command.

- **Options**: The `which` command supports various options to modify its behavior. Some commonly used options include:

  - `-a`: Display all instances of the command found in the `PATH`, rather than just the first one.
  - `-s`: Suppress output. It exits with a status code of 0 if the command is found, or 1 if not found.

- **Output**: The `which` command displays the path of the executable file associated with the command. For example:

  ```shell
  $ which ls
  /bin/ls
  ```

- **Multiple Occurrences**: If the command appears in multiple directories in the `PATH`, `which` by default displays only the first occurrence. The `-a` option can be used to show all occurrences.

- **Command Not Found**: If the specified command is not found in any of the directories in the `PATH`, `which` does not produce any output. It exits with a status code of 1, indicating that the command was not found.

The `which` command is commonly used to determine the location of executable files in the system. It can be helpful for troubleshooting issues related to command execution, verifying the availability of specific commands, and understanding the precedence of commands in the `PATH`.

### help

The `help` command is a built-in command in most Unix-like shells, including Bash and Zsh. It provides help information about shell builtin commands.

```shell
help [command]
```

Key features:

- **List All Builtins**: Running `help` without arguments lists all available builtin commands
- **Specific Help**: `help cd` shows detailed help for the `cd` command
- **Shell-Specific**: Only works for builtin commands, not external programs
- **Quick Reference**: Faster than man pages for builtin commands

Example:
```shell
help           # List all builtin commands
help type      # Get help on the 'type' builtin
```

### type

The `type` command is a built-in command that determines how a command name would be interpreted by the shell.

```shell
type [options] command_name
```

Features:

- **Command Classification**: Shows if command is builtin, alias, function, or external
- **Path Resolution**: Displays the full path for external commands
- **Options**:
  - `-a`: Show all locations containing command
  - `-t`: Show only the type (alias, builtin, file, function)
  - `-p`: Show path for external commands only

Examples:
```shell
type ls        # Shows: ls is aliased to `ls --color=auto`
type cd        # Shows: cd is a shell builtin
type -t grep   # Shows: file
```

### command

The `command` builtin runs a command bypassing shell functions and aliases.

```shell
command [-pVv] command_name [arguments]
```

Options:

- **-p**: Use default PATH, ignoring current PATH
- **-V**: Verbose description of command (like `type`)
- **-v**: Display path of command (like `which`)

Use cases:

- **Bypass Aliases**: `command ls` runs actual `ls`, not alias
- **Bypass Functions**: Ensures you run the real command
- **Path Testing**: `command -v git` checks if git is available

### hash

The `hash` command manages the shell's internal hash table of command locations.

```shell
hash [options] [command]
```

Features:

- **Display Hash Table**: `hash` shows cached command locations
- **Clear Cache**: `hash -r` clears the entire hash table
- **Remove Entry**: `hash -d command` removes specific command from cache
- **Add Entry**: `hash command` adds/updates command in cache

Useful for:

- Understanding command lookup performance
- Forcing re-lookup of moved commands
- Debugging PATH issues

### apropos

The `apropos` command searches manual page names and descriptions for keywords.

```shell
apropos [options] keyword
```

Features:

- **Keyword Search**: Finds commands related to a topic
- **Description Search**: Searches both command names and descriptions
- **Multiple Keywords**: Can search for multiple terms

Options:

- `-a`: All keywords must match (AND logic)
- `-e`: Exact match only
- `-r`: Use regular expressions

Example:
```shell
apropos network    # Find all commands related to networking
apropos "copy file" # Find commands for copying files
```

### whatis

The `whatis` command displays brief descriptions of commands from manual pages.

```shell
whatis command_name
```

Features:

- **One-Line Descriptions**: Shows concise command summaries
- **Quick Lookup**: Faster than reading full man pages
- **Multiple Commands**: Can query multiple commands at once

Example:
```shell
whatis ls cp mv    # Get brief descriptions of ls, cp, and mv
```

### info

The `info` command displays GNU Info documents, which often provide more detailed documentation than man pages.

```shell
info [options] [topic]
```

Features:

- **Hypertext Navigation**: Links between related topics
- **Detailed Documentation**: Often more comprehensive than man pages
- **GNU Focus**: Primarily for GNU tools and programs

Navigation:

- **n**: Next node
- **p**: Previous node
- **u**: Up one level
- **q**: Quit
- **Tab**: Move to next link

### --help Option

Most Unix/Linux commands support the `--help` or `-h` option for quick inline help.

```shell
command --help
command -h
```

Features:

- **Quick Reference**: Immediate help without opening separate viewer
- **Usage Examples**: Often includes common usage patterns
- **Option Summary**: Lists all available command options
- **Universal**: Works with most external commands

Examples:
```shell
ls --help          # Quick help for ls command
grep --help        # Show grep options and usage
tar --help         # Display tar command help
```

Tip: When `--help` doesn't work, try `-h`, and if neither works, use `man command`.

## Text Output and Display

### echo

The `echo` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to display text or variables on the terminal. The `echo` command takes the following general form:

```shell
echo [option(s)] [string(s)]
```

Here are some key points about the `echo` command:

- **Displaying Text**: The primary purpose of `echo` is to display text on the terminal. For example:

  ```shell
  echo Hello, World!
  ```

  This will output "Hello, World!" on the terminal.

- **Escaping Characters**: The `echo` command interprets some special characters in the provided string. For example:

  - `\n` represents a newline character.
  - `\t` represents a tab character.
  - `\\` represents a backslash.
  - `\"` represents a double quote.

- **Expanding Variables**: You can also use `echo` to display the values of variables. When you place a variable within double quotes, its value will be expanded and displayed. For example:

  ```shell
  name="John"
  echo "My name is $name"
  ```

  This will output "My name is John" on the terminal.

- **Options**: The `echo` command supports various options to modify its behavior. Some commonly used options include:

  - `-n`: Suppresses the trailing newline character, allowing you to print text without a line break.
  - `-e`: Enables the interpretation of escape sequences, such as `\n` and `\t`.
  - `-E`: Disables the interpretation of escape sequences.

- **Multiple Arguments**: You can pass multiple strings to the `echo` command, separated by spaces. The command will display each string, separated by spaces. For example:
  ```shell
  echo Hello, World! Have a nice day.
  ```
  This will output "Hello, World! Have a nice day." on the terminal.

The `echo` command is often used in shell scripts for displaying messages, generating output, or providing information to the user. It is a simple yet useful built-in command for printing text and values on the terminal.

## File Operations

### ls

The `ls` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to list files and directories in a directory. The `ls` command takes the following general form:

```shell
ls [option(s)] [file(s)]
```

Here are some key points about the `ls` command:

- **Listing Files and Directories**: The primary purpose of `ls` is to list the files and directories within a specified directory. When used without any arguments, it lists the contents of the current directory. For example:

  ```shell
  ls
  ```

  This will display a list of files and directories in the current directory.

- **Specifying Files or Directories**: You can provide file or directory names as arguments to `ls` to list specific files or directories. For example:

  ```shell
  ls file.txt
  ```

  This will display information about the file named "file.txt".

- **Options**: The `ls` command supports various options to modify its behavior and customize the information displayed. Some commonly used options include:

  - `-l`: Long format display, which provides detailed information about files, such as permissions, ownership, size, and modification time.
  - `-a`: Include hidden files in the listing. Hidden files start with a dot (`.`) in their name.
  - `-h`: Human-readable format, which displays file sizes in a more readable format (e.g., "1K", "10M").
  - `-r`: Reverse the order of the listing.
  - `-t`: Sort the listing by modification time, with the newest files first.

- **Recursive Listing**: You can use the `-R` option to recursively list files and directories within subdirectories. This will display the contents of the specified directory and its subdirectories.

- **Colorized Output**: Depending on the configuration of your shell, the `ls` command may display colorized output to differentiate between different file types and attributes. This can make it easier to distinguish directories, executables, and other file types.

The `ls` command is a fundamental tool for navigating and exploring the file system in Unix-like systems. It provides a convenient way to view file and directory information, list contents, and perform basic file management tasks.

### cat

The `cat` command is a built-in command in Unix-like shells, including both Linux and macOS. It stands for "concatenate." The `cat` command is used to display the contents of one or more files to the terminal or to combine multiple files and output them to a single file or the terminal.

The general syntax of the `cat` command is as follows:

```shell
cat [options] [file(s)]
```

Here are some key points about the `cat` command:

- **Displaying File Contents**: When you provide one or more file names as arguments to the `cat` command, it reads and displays the contents of those files to the terminal. For example:

  ```shell
  cat file.txt
  ```

  This command displays the contents of the file `file.txt` to the terminal.

- **Combining Files**: The `cat` command can also be used to combine multiple files and output them to the terminal or a new file. For example, to combine `file1.txt` and `file2.txt` and display the result:

  ```shell
  cat file1.txt file2.txt
  ```

  To combine `file1.txt` and `file2.txt` and save the result to a new file `combined.txt`:

  ```shell
  cat file1.txt file2.txt > combined.txt
  ```

- **Options**: The `cat` command supports various options to modify its behavior. Some commonly used options include:

  - `-n`: Number the output lines, displaying line numbers along with the file contents.
  - `-E`: Display a `$` character at the end of each line.
  - `-s`: Squeeze multiple adjacent empty lines into a single empty line.

- **Standard Input**: If no file name is provided to the `cat` command, it reads from standard input (stdin). This allows you to use `cat` in combination with pipes (`|`) to process data from other commands or redirect input from files.

The `cat` command is commonly used for viewing file contents, combining files, or redirecting data in shell scripts and command-line operations. It is a simple and versatile tool for working with file contents in Unix-like systems.

### tail

The `tail` command is not a built-in command in Unix-like shells, but it is a commonly used command-line utility for displaying the last part of a file or a stream of data. It is available as a separate executable program in Unix-like systems.

The general syntax of the `tail` command is as follows:

```shell
tail [options] [file]
```

Here are some key points about the `tail` command:

- **Displaying the End of a File**: The primary purpose of `tail` is to display the last part of a file. By default, it shows the last 10 lines of a file. For example:

  ```shell
  tail file.txt
  ```

  This command displays the last 10 lines of the file `file.txt`.

- **Options**: The `tail` command supports various options to customize the information displayed. Some commonly used options include:

  - `-n N`: Specify the number of lines to display from the end of the file. For example, `-n 20` will display the last 20 lines.
  - `-f`: Follow the file and continuously display new lines as they are added. This is useful for monitoring log files in real-time.
  - `-c N`: Specify the number of bytes to display from the end of the file.
  - `-q`: Quiet mode. Suppresses additional information such as headers when multiple files are provided.

- **Reading from Standard Input**: If no file is provided, `tail` reads from standard input (stdin). This allows you to use `tail` in combination with pipes (`|`) to process data from other commands.

- **Additional Functionality**: Depending on the implementation of `tail` and the operating system, it may offer additional features such as displaying the beginning of a file (`head`-like functionality), displaying changes to a file in real-time (`-f` option), or supporting special files like device files.

The `tail` command is commonly used for viewing the last part of log files, monitoring file updates, and extracting relevant information from large files. It is a useful tool for quickly checking the latest entries in files and tracking changes in real-time.

### touch

The `touch` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to create new files or update the timestamps of existing files. The `touch` command takes the following general form:

```shell
touch [option(s)] file(s)
```

Here are some key points about the `touch` command:

- **Creating Files**: The primary purpose of `touch` is to create new files. When used with a file name that doesn't exist, `touch` creates an empty file with that name. For example:

  ```shell
  touch new_file.txt
  ```

  This will create a new file named "new_file.txt" in the current working directory.

- **Updating Timestamps**: In addition to creating new files, `touch` can also be used to update the timestamps of existing files. If the specified file(s) already exist, `touch` updates the access time and modification time of the file(s) to the current time. This can be useful, for example, when you want to mark a file as recently accessed or modified without changing its content.

- **Specifying Multiple Files**: You can provide multiple file names as arguments to `touch` to create or update the timestamps of multiple files in one command. For example:

  ```shell
  touch file1.txt file2.txt file3.txt
  ```

  This will create the files "file1.txt", "file2.txt", and "file3.txt" if they don't already exist, or update their timestamps if they do.

- **Options**: The `touch` command supports various options to modify its behavior. Some commonly used options include:

  - `-a`: Only update the access time of the file(s) and not the modification time.
  - `-m`: Only update the modification time of the file(s) and not the access time.
  - `-c`: Do not create the file if it doesn't already exist. This option is useful when you want to update the timestamp of an existing file without creating a new file if it doesn't exist.

- **Touching Files with Specific Timestamps**: Using the `-t` option, you can specify a specific timestamp for a file. The timestamp should be in the format `[[CC]YY]MMDDhhmm[.ss]`, representing year, month, day, hour, minute, and optional seconds. This can be useful for setting custom timestamps on files.

The `touch` command is a versatile tool for creating new files or updating the timestamps of existing files in Unix-like systems. It provides a convenient way to manage file timestamps and interact with the file system.

### cp

The `cp` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to copy files and directories from one location to another. The `cp` command takes the following general form:

```shell
cp [option(s)] source destination
```

Here are some key points about the `cp` command:

- **Copying Files**: The primary purpose of `cp` is to copy files from a source location to a destination location. The `source` argument specifies the file or files to be copied, and the `destination` argument specifies where the copied files should be placed. For example:

  ```shell
  cp file1.txt file2.txt destination/
  ```

  This will copy the files `file1.txt` and `file2.txt` to the `destination` directory.

- **Copying Directories**: The `cp` command can also be used to copy directories. By default, when you specify a directory as the `source`, `cp` creates a new directory with the same name in the `destination` and copies the contents of the source directory into the destination directory. For example:

  ```shell
  cp -r source_directory destination/
  ```

  The `-r` option is used to copy directories recursively, including all files and subdirectories.

- **Options**: The `cp` command supports various options to modify its behavior. Some commonly used options include:

  - `-r`: Copy directories and their contents recursively.
  - `-i`: Prompt for confirmation before overwriting an existing file.
  - `-v`: Verbose mode, which displays the name of each file as it is copied.
  - `-p`: Preserve the original file's permissions, ownership, timestamps, and other attributes.

- **Preserving Attributes**: By default, `cp` preserves the content of the files being copied but does not preserve their attributes. If you want to preserve the original file's permissions, ownership, timestamps, and other attributes, you can use the `-p` option.

- **Overwriting Files**: If a file with the same name already exists in the destination directory, the `cp` command will overwrite it without prompting by default. If you want to be prompted for confirmation before overwriting an existing file, you can use the `-i` option.

The `cp` command is a versatile tool for copying files and directories in Unix-like systems. It provides a straightforward way to duplicate files or create backups, whether you are copying individual files, multiple files, or entire directory structures.

### mv

The `mv` command is a built-in command in most Unix-like shells, including Bash and Zsh. It stands for "move" and is used to move or rename files and directories. The `mv` command takes the following general form:

```shell
mv [option(s)] source destination
```

Here are some key points about the `mv` command:

- **Moving Files**: The primary purpose of `mv` is to move files from one location to another. For example:

  ```shell
  mv file.txt /path/to/destination/
  ```

  This moves `file.txt` to the specified destination directory.

- **Renaming Files**: `mv` can also be used to rename files by specifying a new name as the destination:

  ```shell
  mv oldname.txt newname.txt
  ```

- **Moving Directories**: You can move entire directories using `mv`:

  ```shell
  mv directory1 /path/to/new/location/
  ```

- **Options**: Common options include:
  - `-i`: Interactive mode, prompts before overwriting
  - `-v`: Verbose mode, shows what is being moved
  - `-f`: Force mode, overwrites without prompting

### ln

The `ln` command is used to create links between files. It can create both hard links and symbolic (soft) links.

```shell
ln [option(s)] target link_name
```

Key points:

- **Hard Links**: By default, `ln` creates hard links:
  ```shell
  ln file.txt hardlink.txt
  ```

- **Symbolic Links**: Use `-s` to create symbolic links:
  ```shell
  ln -s /path/to/file symlink.txt
  ```

- **Options**:
  - `-s`: Create symbolic links
  - `-f`: Force creation, remove existing destination files
  - `-v`: Verbose output

### head

The `head` command displays the first part of files, complementing the `tail` command.

```shell
head [option(s)] [file(s)]
```

Key features:

- **Default Behavior**: Shows the first 10 lines of a file:
  ```shell
  head file.txt
  ```

- **Specify Line Count**: Use `-n` to specify number of lines:
  ```shell
  head -n 20 file.txt
  ```

- **Multiple Files**: Can display headers from multiple files:
  ```shell
  head file1.txt file2.txt
  ```

### less

The `less` command is a pager program for viewing file contents one screen at a time.

```shell
less [option(s)] file
```

Features:

- **Navigation**: Use arrow keys, Page Up/Down, Home/End to navigate
- **Search**: Use `/pattern` to search forward, `?pattern` to search backward
- **Quit**: Press `q` to quit
- **Advantages**: More advanced than `more`, allows backward navigation

### wc

The `wc` command counts lines, words, and characters in files.

```shell
wc [option(s)] [file(s)]
```

Options:

- **Default**: Shows line count, word count, and byte count
- `-l`: Count lines only
- `-w`: Count words only
- `-c`: Count bytes only
- `-m`: Count characters

Example:
```shell
wc -l file.txt  # Count lines in file.txt
```

### rm

The `rm` command is a built-in command in Unix-like shells, including both Linux and macOS. It stands for "remove." The `rm` command is used to delete files and directories from the file system.

The general syntax of the `rm` command is as follows:

```shell
rm [options] file(s)
```

Here are some key points about the `rm` command:

- **Deleting Files**: The primary purpose of `rm` is to delete files from the file system. You can provide one or more file names as arguments, and `rm` will delete those files. For example:

  ```shell
  rm file.txt
  ```

  This command deletes the file `file.txt`.

- **Deleting Directories**: `rm` can also be used to delete directories, but only if they are empty. To delete a directory, you need to use the `-r` or `--recursive` option to remove the directory and its contents recursively. For example:

  ```shell
  rm -r directory
  ```

  This command deletes the directory `directory` and all its contents.

- **Options**: The `rm` command supports various options to modify its behavior. Some commonly used options include:

  - `-f`: Force removal of files without prompting for confirmation, even if they are write-protected.
  - `-i`: Interactive mode. Prompt for confirmation before deleting each file.
  - `-r`, `--recursive`: Recursively remove directories and their contents.
  - `-v`, `--verbose`: Display verbose output, showing each file as it is deleted.

- **Deletion Confirmation**: By default, `rm` does not prompt for confirmation before deleting files. It simply removes the files silently. However, if you use the `-i` option, it will interactively prompt for confirmation before deleting each file.

- **Careful Usage**: The `rm` command permanently deletes files, and the deletion cannot be undone. Exercise caution when using `rm` to avoid accidentally deleting important files. Double-check your command and be mindful of the files you are deleting.

The `rm` command is a powerful tool for removing files and directories from the file system. It is commonly used in shell scripts, system administration tasks, and general file management operations. When using `rm`, ensure that you are targeting the correct files and directories to avoid unintended data loss.

## Directory Operations

### pwd

The `pwd` command is a built-in command in Unix-like shells, including both Linux and macOS. It stands for "print working directory." The `pwd` command is used to display the current working directory, which is the directory in the file system that the user is currently in.

The `pwd` command does not take any arguments or options. When you run `pwd` without any additional parameters, it simply prints the absolute path of the current working directory to the terminal.

Here's an example usage of the `pwd` command:

```shell
$ pwd
/home/user/Documents
```

In this example, the `pwd` command displays the absolute path of the current working directory as `/home/user/Documents`.

The `pwd` command is useful in shell scripts or when navigating the file system. It allows you to quickly determine the current directory, which can be helpful for referencing files or performing operations relative to the current working directory.

### cd

The `cd` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to change the current working directory within the shell. The `cd` command takes the following general form:

```shell
cd [directory]
```

Here are some key points about the `cd` command:

- **Changing the Working Directory**: The primary purpose of `cd` is to change the current working directory to the specified directory. The `directory` argument can be an absolute path or a relative path. If no `directory` argument is provided, `cd` changes the working directory to the user's home directory.

- **Absolute and Relative Paths**: An absolute path specifies the complete path from the root directory to the desired directory. For example, `/home/user/Documents` is an absolute path. A relative path specifies the path relative to the current working directory. For example, `Documents` is a relative path if the current working directory is `/home/user`.

- **Navigating Directories**: With `cd`, you can navigate through different directories in the file system. For example:

  ```shell
  cd /path/to/directory
  ```

  This changes the working directory to `/path/to/directory`. If the specified directory exists and the user has appropriate permissions, the working directory will be updated accordingly.

- **Special Directories**: The `cd` command recognizes some special directory names:

  - `.` (dot): Represents the current directory. Running `cd .` has no effect since it stays in the current directory.
  - `..` (dot-dot): Represents the parent directory. Running `cd ..` changes the working directory to the parent directory.

- **Home Directory**: If you run `cd` without specifying a directory, it changes the working directory to the user's home directory. The home directory is typically the directory where the user's personal files and configurations are stored.

- **Using Variables**: You can use environment variables or shell variables as arguments to `cd`. For example, `cd $HOME` changes the working directory to the value of the `HOME` environment variable.

- **Error Handling**: If the specified directory does not exist or the user does not have appropriate permissions to access it, `cd` will display an error message.

The `cd` command is a fundamental tool for navigating the file system within a shell session. It allows you to move between directories, explore the file hierarchy, and perform operations within different directories.

### mkdir

The `mkdir` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to create new directories (also known as folders) within the file system. The `mkdir` command takes the following general form:

```shell
mkdir [option(s)] directory_name
```

Here are some key points about the `mkdir` command:

- **Creating Directories**: The primary purpose of `mkdir` is to create new directories. The `directory_name` argument specifies the name of the directory to be created. For example:

  ```shell
  mkdir new_directory
  ```

  This will create a new directory named "new_directory" in the current working directory.

- **Creating Nested Directories**: You can create directories within directories, also known as nested directories or subdirectories, by providing the full path of the directory you want to create. For example:

  ```shell
  mkdir -p parent_directory/child_directory
  ```

  The `-p` option is used to create parent directories if they don't already exist. In this example, it creates a directory named "parent_directory" and within it, creates a subdirectory named "child_directory".

- **Options**: The `mkdir` command supports various options to modify its behavior. Some commonly used options include:

  - `-p`: Create parent directories if they don't already exist. This option is useful when creating nested directories.
  - `-m`: Set the permissions (mode) of the newly created directory. You can specify the permissions using a numeric mode or symbolic notation.

- **Multiple Directories**: You can specify multiple directory names as arguments to `mkdir` to create multiple directories in one command. For example:

  ```shell
  mkdir dir1 dir2 dir3
  ```

  This will create three directories named "dir1", "dir2", and "dir3" in the current working directory.

- **Error Handling**: If a directory with the same name already exists in the specified location, `mkdir` will display an error message and not create a new directory. To force the creation of a directory, you can use the `-f` option.

The `mkdir` command is a simple and essential tool for creating directories in Unix-like systems. It allows you to organize your files and establish a directory structure that suits your needs.

### dir

The `dir` command is a built-in command in the Windows command prompt (CMD) and PowerShell. It is used to display a list of files and subdirectories within a directory. The `dir` command takes the following general form:

```shell
dir [option(s)] [directory]
```

Here are some key points about the `dir` command:

- **Listing Files and Directories**: The primary purpose of `dir` is to list the files and directories within a specified directory. When used without any arguments, it lists the contents of the current directory. For example:

  ```shell
  dir
  ```

  This will display a list of files and directories in the current directory.

- **Specifying Directory**: You can provide a directory name as an argument to `dir` to list the contents of a specific directory. For example:

  ```shell
  dir C:\path\to\directory
  ```

  This will display a list of files and directories in the specified directory.

- **Options**: The `dir` command supports various options to modify its behavior and customize the information displayed. Some commonly used options include:

  - `/A`: Display files with specified attributes. For example, `/A:H` displays hidden files, `/A:D` displays directories, and `/A:-D` excludes directories.
  - `/B`: Display bare format, which lists only the file and directory names without additional information.
  - `/S`: Recursively list files and directories in the specified directory and its subdirectories.
  - `/W`: Wide format display, which lists files and directories in multiple columns.

- **Filtering and Sorting**: The `dir` command supports wildcard characters to filter the list of files and directories. For example, `dir *.txt` displays only files with the ".txt" extension. Additionally, you can use the `/O` option to sort the list by a specific attribute, such as name, size, or modification time.

- **Colorized Output**: By default, the `dir` command in Windows command prompt displays colorized output to differentiate between different file types and attributes. This can make it easier to distinguish directories, executables, and other file types.

The `dir` command is a useful tool for listing files and directories in the Windows command prompt or PowerShell. It provides a simple way to view file and directory information, navigate the file system, and perform basic file management tasks.

## File Permissions and Ownership

### chmod

The `chmod` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to change the permissions of files and directories in the file system. The `chmod` command takes the following general form:

```shell
chmod [option(s)] mode file(s)
```

Here are some key points about the `chmod` command:

- **Changing Permissions**: The primary purpose of `chmod` is to change the permissions of files and directories. The `mode` argument specifies the new permissions to be set, and the `file(s)` argument specifies the file(s) to which the permissions should be applied. For example:

  ```shell
  chmod u+r file.txt
  ```

  This command adds read permission (`+r`) for the owner (`u`) of the file "file.txt".

- **Permission Modes**: The `mode` argument can be specified in various ways to indicate the desired permissions. There are three primary types of permissions: read (`r`), write (`w`), and execute (`x`). The permissions can be assigned to three different categories: owner (`u`), group (`g`), and others (`o`). Additionally, you can use the `+` and `-` symbols to add or remove permissions, and the `=` symbol to set permissions explicitly.

- **Numeric Modes**: Instead of using symbolic notation, you can also specify the permissions using a numeric mode. In this mode, each permission is represented by a digit: read (`4`), write (`2`), and execute (`1`). The digits are summed up to determine the overall permission value. For example, `chmod 644 file.txt` sets read and write permissions for the owner, and read-only permissions for the group and others.

- **Options**: The `chmod` command supports various options to modify its behavior. Some commonly used options include:

  - `-R`: Recursively change the permissions of directories and their contents.
  - `-v`: Verbose mode, which displays a message for each file whose permissions are changed.
  - `-c`: Only display a message if the permissions of a file are actually changed.

- **Symbolic Links**: By default, `chmod` follows symbolic links and changes the permissions of the target file or directory. If you want to change the permissions of the symbolic link itself, you can use the `-h` option.

- **Octal vs. Symbolic Notation**: The symbolic notation (`u+r`, `g-w`, etc.) is more human-readable and flexible, allowing you to add or remove specific permissions. On the other hand, octal notation (`644`, `755`, etc.) is more compact and allows you to set the permissions explicitly.

The `chmod` command is a powerful tool for managing file and directory permissions in Unix-like systems. It provides fine-grained control over who can read, write, and execute files, allowing you to secure your system and control access to sensitive information.

### chown

The `chown` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to change the ownership of files and directories in the file system. The `chown` command takes the following general form:

```shell
chown [option(s)] owner[:group] file(s)
```

Here are some key points about the `chown` command:

- **Changing Ownership**: The primary purpose of `chown` is to change the ownership of files and directories. The `owner` argument specifies the new owner, and the optional `group` argument specifies the new group ownership. The `file(s)` argument specifies the file(s) to which the ownership should be applied. For example:

  ```shell
  chown user:group file.txt
  ```

  This command changes the owner of the file "file.txt" to "user" and the group ownership to "group".

- **Owner and Group**: The ownership of a file or directory in Unix-like systems is typically associated with a user and a group. The `owner` argument specifies the new user owner, while the optional `group` argument specifies the new group owner. If the `group` argument is omitted, the group ownership remains unchanged.

- **User and Group Identification**: The `owner` and `group` arguments can be specified using either the actual name or the corresponding numeric identifier (UID or GID). You can use the `id` command to retrieve the numeric identifiers for users and groups.

- **Options**: The `chown` command supports various options to modify its behavior. Some commonly used options include:

  - `-R`: Recursively change the ownership of directories and their contents.
  - `-v`: Verbose mode, which displays a message for each file whose ownership is changed.
  - `-c`: Only display a message if the ownership of a file is actually changed.

- **Symbolic Links**: By default, `chown` follows symbolic links and changes the ownership of the target file or directory. If you want to change the ownership of the symbolic link itself, you can use the `-h` option.

- **Superuser Privileges**: In order to change the ownership of files or directories owned by other users, you typically need superuser (root) privileges. You can use the `sudo` command before `chown` to execute it with elevated privileges.

The `chown` command is a powerful tool for managing file and directory ownership in Unix-like systems. It allows you to transfer ownership of files, reassign group ownership, and ensure proper access control within your file system.

## System Information

### ps

The `ps` command is not a built-in command in Unix-like shells, but it is a commonly used command-line utility for displaying information about running processes. It is available as a separate executable program in Unix-like systems.

The general syntax of the `ps` command is as follows:

```shell
ps [options]
```

Here are some key points about the `ps` command:

- **Displaying Process Information**: The primary purpose of `ps` is to display information about currently running processes on the system. When run without any options, it lists processes owned by the current user associated with the current terminal.

- **Options**: The `ps` command supports various options to filter and customize the information displayed. Some commonly used options include:

  - `-e`: Display information about all processes in the system, not just those owned by the current user.
  - `-f`: Display a full-format listing that includes additional details about each process.
  - `-l`: Display a long-format listing that includes additional information such as process state, CPU usage, and start time.
  - `-u`: Specify a username to only display processes owned by that user.
  - `-p`: Specify one or more process IDs to display information about specific processes.

- **Process Information**: The information displayed by `ps` includes details about the processes, such as:

  - Process ID (PID): A unique identifier assigned to each running process.
  - Parent Process ID (PPID): The ID of the parent process that spawned the current process.
  - Process State: Indicates the current state of the process (e.g., running, sleeping, stopped, zombie).
  - CPU Usage: Provides information about the CPU usage of each process.
  - Memory Usage: Displays memory-related information, such as resident set size (RSS) and virtual memory size (VSZ).
  - Command: Shows the command or program associated with the process.

- **Output Formatting**: The `ps` command allows you to customize the output format using various options. You can choose different output styles, sort the output by specific columns, and control the level of detail displayed.

- **Additional Functionality**: `ps` provides additional functionality beyond basic process listing, including monitoring, filtering, and process control capabilities. It allows you to send signals to processes, track changes in process status, and gather system-wide process statistics.

The `ps` command is a versatile tool for examining running processes, monitoring system activity, and diagnosing issues related to process management on a Unix-like system. It is commonly used in shell scripting, system administration, and troubleshooting tasks.

### top

The `top` command displays running processes and system resource usage in real-time.

```shell
top [option(s)]
```

Features:

- **Real-time Display**: Shows CPU usage, memory usage, and running processes
- **Interactive**: Can sort by different columns, kill processes
- **Common Keys**:
  - `q`: Quit
  - `k`: Kill a process
  - `M`: Sort by memory usage
  - `P`: Sort by CPU usage

### htop

The `htop` command is an enhanced version of `top` with a more user-friendly interface.

```shell
htop [option(s)]
```

Advantages over `top`:

- **Color-coded**: Uses colors for better readability
- **Mouse Support**: Can click to select and interact
- **Tree View**: Shows process relationships
- **Easier Navigation**: More intuitive interface

### free

The `free` command displays memory usage information.

```shell
free [option(s)]
```

Options:

- `-h`: Human-readable format (MB, GB)
- `-s`: Continuous updates every N seconds
- `-t`: Show total memory

Example:
```shell
free -h  # Show memory usage in human-readable format
```

### uptime

The `uptime` command shows how long the system has been running.

```shell
uptime
```

Displays:

- Current time
- How long system has been running
- Number of users currently logged in
- System load averages

### lsof

`lsof` is not a built-in command in Unix-like shells, but it is a powerful utility for displaying information about files opened by processes on a system. It stands for "list open files." The `lsof` command is typically available as a separate executable program in Unix-like systems.

The general syntax of the `lsof` command is as follows:

```shell
lsof [options]
```

Here are some key points about the `lsof` command:

- **Displaying Open Files**: The primary purpose of `lsof` is to display information about files opened by processes. When run without any options, it lists all open files on the system.

- **Options**: The `lsof` command supports various options to filter and customize the information displayed. Some commonly used options include:

  - `-p`: Specify a process ID to only display files opened by a specific process.
  - `-u`: Specify a username to only display files opened by a specific user.
  - `-i`: Display files related to network connections (e.g., TCP/IP sockets).
  - `-c`: Specify a command name to only display files opened by processes running that command.
  - `-r`: Repeat the `lsof` command at regular intervals to continuously monitor open files.

- **File Information**: The information displayed by `lsof` includes details about the open files, such as:

  - File descriptor (FD): A unique identifier associated with an open file.
  - File type: Indicates whether it is a regular file, directory, socket, pipe, etc.
  - File name or path: The name or path of the file.
  - Process ID (PID): The ID of the process that opened the file.
  - User and group: The user and group associated with the process.
  - Access mode: The access mode or permissions of the file.

- **Network Connections**: `lsof` can also display information about network connections, such as open TCP/IP and UDP sockets. This can be useful for monitoring network activity and identifying processes using specific ports.

- **Additional Functionality**: `lsof` can provide more advanced information, including details about shared libraries, mounted filesystems, and memory-mapped files.

The `lsof` command is a powerful tool for inspecting and troubleshooting open files and processes on a Unix-like system. It helps identify which processes have certain files open, reveal resource usage, and diagnose issues related to file locking, network connections, or resource contention.

## System Administration

### sudo

The `sudo` command is a built-in command in most Unix-like systems, including Linux and macOS. It stands for "Superuser Do" and is used to execute a command with elevated privileges or as another user, typically the root user.

Here are some key points about the `sudo` command:

- **Elevated Privileges**: The primary purpose of `sudo` is to execute a command with elevated privileges. By default, this means running the command as the root user, which has administrative privileges. This allows authorized users to perform administrative tasks or execute commands that require higher permissions.

- **Authorization**: Before executing a command with `sudo`, the user is typically prompted to enter their own password. Once authenticated, `sudo` checks the user's privileges and the command's configuration to determine whether the user is allowed to execute the command with elevated privileges.

- **Command Syntax**: The general syntax for using `sudo` is as follows:

  ```shell
  sudo [option(s)] command [arguments]
  ```

  - `command` is the command you want to execute with elevated privileges.
  - `arguments` are any additional parameters or arguments required by the command.

- **Options**: The `sudo` command supports various options to modify its behavior. Some commonly used options include:

  - `-u user`: Execute the command as the specified user instead of the root user.
  - `-i`: Run the command in a new shell with the environment variables of the target user.
  - `-s`: Run the command in a shell with elevated privileges or as another user.

- **Configuration**: The behavior of `sudo` can be configured through the `sudoers` file, which is typically located at `/etc/sudoers`. The file defines who is allowed to use `sudo`, which commands they can execute, and any additional restrictions or options.

- **Security Considerations**: It's important to use `sudo` with caution to prevent unauthorized or malicious use. Only authorized users should be granted `sudo` privileges, and the commands executed with `sudo` should be verified and trusted to avoid potential security risks.

The `sudo` command is widely used to perform administrative tasks, manage system configurations, install software, and execute commands that require elevated privileges. It allows authorized users to temporarily act as superusers or other privileged users, providing a secure and controlled way to perform administrative operations on Unix-like systems.

### env

The `env` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to display or modify the environment variables within the current shell session or to execute a command in a modified environment. The `env` command takes the following general form:

```shell
env [option(s)] [name=value ...] [command]
```

Here are some key points about the `env` command:

- **Displaying Environment Variables**: When used without any options or arguments, the `env` command displays the current environment variables. It provides a list of variable names and their corresponding values.

- **Modifying Environment Variables**: The `env` command can be used to modify the environment variables within the current shell session. You can specify new values for existing variables or define new variables using the `name=value` syntax. For example:

  ```shell
  env VAR=value command
  ```

  This sets the value of the environment variable `VAR` to "value" and then executes the specified `command` in the modified environment.

- **Executing Commands in a Modified Environment**: By providing a command as an argument to the `env` command, you can execute that command within a modified environment. This allows you to override or add environment variables specifically for that command. For example:

  ```shell
  env VAR=value command
  ```

  This executes `command` with the environment variable `VAR` set to "value" while keeping the rest of the environment variables intact.

- **Options**: The `env` command supports various options to modify its behavior. Some commonly used options include:
  - `-i`: Clear all environment variables and start with a clean environment.
  - `-u variable`: Unset (remove) the specified variable from the environment.
  - `-S separator`: Specify a custom separator character for variable assignments.

The `env` command is often used in shell scripting to control the environment variables for a specific command or to create clean environments for executing commands. It provides flexibility in managing the environment within a shell session and allows you to modify or override specific variables as needed.

### whoami

The `whoami` command displays the current username.

```shell
whoami
```

Simple command that prints the effective user ID.

### id

The `id` command displays user and group IDs.

```shell
id [username]
```

Shows:

- User ID (UID)
- Group ID (GID) 
- All group memberships

Example:
```shell
id        # Show current user's IDs
id john   # Show john's IDs
```

### uname

The `uname` command displays system information.

```shell
uname [option(s)]
```

Options:

- `-a`: All information
- `-s`: Kernel name
- `-r`: Kernel release
- `-m`: Machine hardware name
- `-o`: Operating system

### umask

The `umask` command sets default file permissions.

```shell
umask [mode]
```

Features:

- **Display**: `umask` shows current mask
- **Set**: `umask 022` sets new default permissions
- **Effect**: Determines default permissions for new files/directories

### kill

The `kill` command terminates processes by PID.

```shell
kill [signal] PID
```

Common signals:

- `kill PID`: Terminate gracefully (SIGTERM)
- `kill -9 PID`: Force kill (SIGKILL)
- `kill -STOP PID`: Stop process
- `kill -CONT PID`: Continue stopped process

### killall

The `killall` command terminates processes by name.

```shell
killall [option(s)] process_name
```

Examples:

- `killall firefox`: Kill all Firefox processes
- `killall -9 chrome`: Force kill all Chrome processes

### jobs

The `jobs` command lists active jobs in the current shell.

```shell
jobs [option(s)]
```

Shows background and suspended jobs with job numbers.

### bg

The `bg` command puts jobs in the background.

```shell
bg [job_spec]
```

Example:
```shell
bg %1  # Put job 1 in background
```

### fg

The `fg` command brings jobs to the foreground.

```shell
fg [job_spec]
```

Example:
```shell
fg %1  # Bring job 1 to foreground
```

### nohup

The `nohup` command runs commands immune to hangups.

```shell
nohup command [args]
```

Features:

- Prevents termination when terminal closes
- Redirects output to `nohup.out`
- Useful for long-running processes

### history

The `history` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to display or manipulate the command history, which is a record of previously executed commands in the current shell session. The `history` command takes the following general form:

```shell
history [option(s)]
```

Here are some key points about the `history` command:

- **Displaying Command History**: When used without any options, the `history` command displays a numbered list of previously executed commands. By default, it shows the most recent commands at the bottom of the list. Each command is assigned a unique number, starting from 1.

- **Limiting the Displayed History**: You can use the `-n` option followed by a number to limit the number of commands displayed. For example, `history -n 10` displays the last 10 commands in the history.

- **Executing Previous Commands**: To execute a command from the history, you can use the `!` (exclamation mark) followed by the command number. For example, `!5` executes the command with number 5 from the history.

- **Searching the History**: You can search the history for a specific command using the `Ctrl+R` keyboard shortcut. This opens an interactive search prompt where you can type a portion of the command and press `Enter` to execute the matching command.

- **Options**: The `history` command supports various options to modify its behavior. Some commonly used options include:

  - `-c`: Clear the command history, removing all previously executed commands.
  - `-w`: Write the current command history to the history file specified by the `HISTFILE` environment variable. This ensures that the history is preserved across shell sessions.
  - `-a`: Append the current session's command history to the history file without overwriting it.

- **Customizing History Settings**: The behavior of the `history` command can be customized by modifying the shell's history-related variables. For example, you can control the maximum number of commands to keep in the history (`HISTSIZE`), configure the history file location (`HISTFILE`), or ignore certain commands from being recorded (`HISTIGNORE`).

The `history` command is useful for recalling previously executed commands, reusing or modifying them, and reviewing the command history for troubleshooting or auditing purposes. It provides an efficient way to navigate and manage your command history within a shell session.

## Disk and Storage

### df

The `df` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to display information about the disk space usage on file systems. The `df` command takes the following general form:

```shell
df [option(s)] [file(s)]
```

Here are some key points about the `df` command:

- **Displaying Disk Space**: The primary purpose of `df` is to display information about the disk space usage on file systems. When used without any arguments, it lists the disk space usage for all mounted file systems. For example:

  ```shell
  df
  ```

  This will display a table showing the total, used, and available disk space on all mounted file systems.

- **Specifying File Systems**: You can provide file system names or mount points as arguments to `df` to display the disk space usage for specific file systems. For example:

  ```shell
  df /dev/sda1 /home
  ```

  This will display the disk space usage for the file system associated with `/dev/sda1` and the `/home` directory.

- **Options**: The `df` command supports various options to modify its behavior and customize the information displayed. Some commonly used options include:

  - `-h` or `--human-readable`: Display sizes in human-readable format (e.g., 1K, 1M, 1G) rather than in bytes.
  - `-a` or `--all`: Include all file systems, including those that are not mounted.
  - `-T` or `--print-type`: Display the file system type for each file system.

- **File System Information**: The information displayed by `df` typically includes the following columns:

  - `Filesystem`: The file system name or mount point.
  - `Size`: The total size of the file system.
  - `Used`: The amount of disk space used.
  - `Available`: The amount of disk space available for new files.
  - `Use%`: The percentage of disk space used.
  - `Mounted on`: The mount point of the file system.

- **Remote File Systems**: `df` can also display information about disk space usage on remote file systems (e.g., NFS shares) if they are mounted on the local system.

The `df` command is a useful tool for monitoring disk space usage on Unix-like systems. It helps you understand the available space, identify potential storage issues, and manage disk usage effectively.

### du

The `du` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to estimate the disk space usage of files and directories. The `du` command takes the following general form:

```shell
du [option(s)] [file(s) or directory]
```

Here are some key points about the `du` command:

- **Estimating Disk Space Usage**: The primary purpose of `du` is to estimate the disk space usage of files and directories. When used without any arguments, it calculates the disk space usage for the current directory. For example:

  ```shell
  du
  ```

  This will display the disk space usage for the current directory and its subdirectories.

- **Specifying Files or Directories**: You can provide file names or directory paths as arguments to `du` to calculate the disk space usage for specific files or directories. For example:

  ```shell
  du file.txt directory
  ```

  This will display the disk space usage for the file "file.txt" and the "directory" directory.

- **Options**: The `du` command supports various options to modify its behavior and customize the information displayed. Some commonly used options include:

  - `-h` or `--human-readable`: Display sizes in human-readable format (e.g., 1K, 1M, 1G) rather than in blocks.
  - `-s` or `--summarize`: Display only the total disk space usage of the specified files or directories.
  - `-c` or `--total`: Display a grand total of the disk space usage for all specified files or directories.

- **Disk Space Usage Information**: The information displayed by `du` typically includes the following columns:

  - `Size`: The total size of the file or directory.
  - `File or Directory Name`: The name of the file or directory.

- **Recursive Calculation**: By default, `du` calculates the disk space usage recursively, including all files and directories within the specified directory. This allows you to see the cumulative size of the entire directory tree.

- **Disk Space Usage Units**: The disk space usage is usually displayed in blocks, which are typically 1 kilobyte (KB) on most systems. You can use the `-h` option to display sizes in a more human-readable format.

The `du` command is a useful tool for analyzing disk space usage on Unix-like systems. It helps you identify space-consuming files and directories, track storage usage, and make informed decisions about managing disk space efficiently.

## Text Processing

### sort

The `sort` command sorts lines of text files.

```shell
sort [option(s)] [file(s)]
```

Key features:

- **Default**: Sorts lines alphabetically
- **Options**:
  - `-n`: Numerical sort
  - `-r`: Reverse sort order
  - `-u`: Remove duplicate lines
  - `-k`: Sort by specific column/field

Example:
```shell
sort -n numbers.txt  # Sort numerically
```

### uniq

The `uniq` command reports or omits repeated lines.

```shell
uniq [option(s)] [file]
```

Features:

- **Default**: Removes adjacent duplicate lines
- **Options**:
  - `-c`: Count occurrences
  - `-d`: Show only duplicate lines
  - `-u`: Show only unique lines

Note: Usually used with `sort` first to group duplicates.

### cut

The `cut` command extracts sections from each line of files.

```shell
cut [option(s)] [file(s)]
```

Options:

- `-d`: Specify delimiter
- `-f`: Select fields
- `-c`: Select characters

Example:
```shell
cut -d',' -f1,3 data.csv  # Extract 1st and 3rd columns from CSV
```

### sed

The `sed` command is a stream editor for filtering and transforming text.

```shell
sed [option(s)] 'command' [file(s)]
```

Common uses:

- **Substitute**: `sed 's/old/new/g' file.txt`
- **Delete lines**: `sed '2d' file.txt` (delete line 2)
- **Print specific lines**: `sed -n '1,5p' file.txt`

### awk

The `awk` command is a powerful text processing tool and programming language.

```shell
awk 'pattern { action }' [file(s)]
```

Examples:

- **Print specific columns**: `awk '{print $1, $3}' file.txt`
- **Sum numbers**: `awk '{sum += $1} END {print sum}' numbers.txt`
- **Pattern matching**: `awk '/pattern/ {print}' file.txt`

### tr

The `tr` command translates or deletes characters.

```shell
tr [option(s)] set1 [set2]
```

Common uses:

- **Convert case**: `tr 'a-z' 'A-Z'` (lowercase to uppercase)
- **Delete characters**: `tr -d '0-9'` (remove digits)
- **Squeeze repeats**: `tr -s ' '` (squeeze multiple spaces)

### grep

The `grep` command is not a built-in command in Unix-like shells, but it is a widely used command-line tool for searching patterns in text. It is available as a separate executable program in Unix-like systems. The `grep` command takes the following general form:

```shell
grep [option(s)] pattern [file(s)]
```

Here are some key points about the `grep` command:

- **Searching for Patterns**: The primary purpose of `grep` is to search for patterns in text files. The `pattern` argument specifies the pattern you want to search for. For example:

  ```shell
  grep "example" file.txt
  ```

  This command searches for the pattern "example" in the file "file.txt" and displays all lines that contain the pattern.

- **Specifying Files**: You can provide one or more file names as arguments to `grep` to search within specific files. If no file name is provided, `grep` reads from standard input (e.g., data piped from another command). You can also use wildcards or file globs to specify multiple files. For example:

  ```shell
  grep "pattern" *.txt
  ```

  This command searches for the pattern "pattern" in all files with the `.txt` extension in the current directory.

- **Options**: The `grep` command supports various options to modify its behavior and customize the search. Some commonly used options include:

  - `-i` or `--ignore-case`: Perform case-insensitive matching.
  - `-v` or `--invert-match`: Invert the match, displaying lines that do not contain the pattern.
  - `-r` or `--recursive`: Recursively search subdirectories.
  - `-n` or `--line-number`: Display line numbers along with matching lines.

- **Regular Expressions**: `grep` uses regular expressions (regex) to match patterns. This allows for flexible and powerful pattern matching. You can use regular expression metacharacters and quantifiers to specify complex patterns. For example, `grep "a.*b"` matches lines that have an "a" followed by any number of characters and then a "b".

- **Output Formatting**: By default, `grep` displays matching lines in their entirety. However, you can use additional options (such as `-o`) to display only the matched portions or customize the output format.

The `grep` command is a versatile tool for searching and filtering text based on patterns. It is commonly used in shell scripting, data processing, log analysis, and various other tasks that involve searching for specific patterns within files or streams of text.

## Network

### ping

The `ping` command sends ICMP echo requests to test network connectivity.

```shell
ping [option(s)] destination
```

Features:

- **Basic Usage**: `ping google.com`
- **Count**: `ping -c 4 google.com` (send 4 packets)
- **Interval**: `ping -i 2 google.com` (2-second interval)

### curl

The `curl` command transfers data from or to servers.

```shell
curl [option(s)] URL
```

Common uses:

- **Download**: `curl -O https://example.com/file.zip`
- **POST Data**: `curl -X POST -d "data" https://api.example.com`
- **Headers**: `curl -H "Content-Type: application/json" URL`
- **Follow Redirects**: `curl -L URL`

### wget

The `wget` command downloads files from web servers.

```shell
wget [option(s)] URL
```

Features:

- **Recursive**: `wget -r https://example.com`
- **Resume**: `wget -c partially_downloaded_file`
- **Mirror**: `wget -m https://example.com`
- **Background**: `wget -b URL`

### ssh

The `ssh` command provides secure shell access to remote systems.

```shell
ssh [options] user@hostname
```

Examples:

- **Basic**: `ssh user@server.com`
- **Port**: `ssh -p 2222 user@server.com`
- **Key**: `ssh -i ~/.ssh/key.pem user@server.com`
- **Execute Command**: `ssh user@server.com 'ls -la'`

### scp

The `scp` command securely copies files between hosts.

```shell
scp [options] source destination
```

Examples:

- **Upload**: `scp file.txt user@server.com:/path/`
- **Download**: `scp user@server.com:/path/file.txt .`
- **Recursive**: `scp -r directory/ user@server.com:/path/`

## Archive and Compression

### tar

The `tar` command archives files and directories.

```shell
tar [options] archive_name files
```

Common operations:

- **Create**: `tar -cvf archive.tar files/`
- **Extract**: `tar -xvf archive.tar`
- **List**: `tar -tvf archive.tar`
- **Compress**: `tar -czvf archive.tar.gz files/`
- **Extract Compressed**: `tar -xzvf archive.tar.gz`

### gzip

The `gzip` command compresses files.

```shell
gzip [options] files
```

Features:

- **Compress**: `gzip file.txt` (creates file.txt.gz)
- **Decompress**: `gunzip file.txt.gz`
- **Keep Original**: `gzip -k file.txt`
- **Best Compression**: `gzip -9 file.txt`

### zip

The `zip` command creates compressed archives.

```shell
zip [options] archive.zip files
```

Examples:

- **Create**: `zip archive.zip file1.txt file2.txt`
- **Recursive**: `zip -r archive.zip directory/`
- **Extract**: `unzip archive.zip`
- **List**: `unzip -l archive.zip`

## File Search

### locate

The `locate` command finds files using a pre-built database.

```shell
locate [options] pattern
```

Features:

- **Fast Search**: Uses indexed database
- **Update Database**: `updatedb` (usually requires sudo)
- **Case Insensitive**: `locate -i pattern`
- **Count**: `locate -c pattern`

### whereis

The `whereis` command locates binary, source, and manual page files.

```shell
whereis [options] command
```

Searches for:

- Binary files
- Source code files
- Manual pages

Example:
```shell
whereis ls  # Find ls binary, source, and man page
```

### find

The `find` command is not a built-in command in Unix-like shells, but it is a powerful command-line tool for searching files and directories based on various criteria. It is available as a separate executable program in Unix-like systems. The `find` command takes the following general form:

```shell
find [path] [expression]
```

Here are some key points about the `find` command:

- **Searching for Files and Directories**: The primary purpose of `find` is to search for files and directories in a given directory hierarchy. The `path` argument specifies the starting directory for the search. For example:

  ```shell
  find /path/to/search -name "*.txt"
  ```

  This command searches for all files with the `.txt` extension in the `/path/to/search` directory and its subdirectories.

- **Expression**: The `expression` argument specifies the criteria or conditions to be used for the search. It can include various options, tests, and actions. Some commonly used expressions include:

  - `-name pattern`: Match files and directories with a specific name or pattern.
  - `-type type`: Match files of a specific type (e.g., regular files, directories, symbolic links).
  - `-size size`: Match files based on their size.
  - `-mtime n`: Match files based on their modification time.
  - `-user user`: Match files owned by a specific user.
  - `-exec command {} \;`: Execute a command on each matched file or directory.

- **Options**: The `find` command supports various options to modify its behavior and customize the search. Some commonly used options include:

  - `-depth`: Process directories' contents before the directories themselves.
  - `-maxdepth n`: Limit the search depth to a specified level.
  - `-print`: Print the paths of matched files and directories.
  - `-delete`: Delete matched files and directories.
  - `-execdir command {} \;`: Execute a command in the directory of each matched file.

- **Regular Expressions**: `find` supports regular expressions for pattern matching in expressions like `-name` and `-regex`. Regular expressions provide powerful pattern matching capabilities.

- **Complex Searches**: `find` allows you to combine multiple expressions using logical operators such as `-and`, `-or`, and `-not`. This enables you to perform complex searches based on various conditions.

The `find` command is a versatile tool for searching files and directories in Unix-like systems. It is commonly used for tasks such as finding files based on name, type, size, modification time, and ownership. `find` provides a flexible and powerful way to locate and process files and directories in complex directory hierarchies.

## Shell and Scripting

### eval

The `eval` command is a built-in command in most Unix-like shells, including Bash and Zsh. It is used to evaluate and execute a command that is constructed dynamically or stored as a string. The `eval` command takes the following general form:

```shell
eval [option(s)] [command_string]
```

Here are some key points about the `eval` command:

- **Dynamic Command Execution**: The primary purpose of `eval` is to evaluate and execute a command that is constructed dynamically or stored as a string. This allows you to build and execute commands programmatically at runtime. For example:

  ```shell
  command="ls -l"
  eval $command
  ```

  This will execute the command `ls -l`, which is stored in the variable `command`.

- **Expanding Variables**: When a command string is passed to `eval`, it undergoes variable expansion. This means that any variables within the command string will be expanded and their values will be used during command execution. For example:

  ```shell
  dir="Documents"
  eval ls $dir
  ```

  This will execute the command `ls Documents`, where the variable `$dir` is expanded to its value (`Documents`).

- **Evaluating Expressions**: The `eval` command can also evaluate arithmetic expressions. When an arithmetic expression is passed to `eval`, it is evaluated and the result is returned. For example:

  ```shell
  expression="2 + 3 * 4"
  eval echo $(( $expression ))
  ```

  This will evaluate the expression `2 + 3 * 4`, which equals 14, and the result will be displayed as output.

- **Command Substitution**: The `eval` command can also be used with command substitution, denoted by `$()` or backticks. Command substitution allows you to capture the output of a command and use it as part of another command. For example:
  ```shell
  result=$(ls)
  eval echo $result
  ```
  This will execute the `ls` command, capture its output, store it in the variable `result`, and then display the contents of `result` using `eval`.

It's important to note that the `eval` command can be powerful but also potentially dangerous if used incorrectly or with untrusted input. Care should be taken to ensure that the evaluated command string is secure and properly constructed to avoid unintended consequences or security vulnerabilities.

The `eval` command is often used in advanced shell scripting scenarios where command construction or dynamic evaluation is required. It allows you to build and execute commands at runtime, expanding variables and evaluating expressions as needed.