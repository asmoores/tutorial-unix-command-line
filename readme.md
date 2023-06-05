# Linux Command Line Tutorial

## What is a shell?

A Unix shell is a command-line interface (CLI) or a text-based user interface (TUI) used in Unix-like operating systems. It provides a way for users to interact with the operating system by entering commands and receiving output. The shell acts as an intermediary between the user and the operating system, interpreting and executing commands.

The shell allows users to launch programs, manage files and directories, manipulate data, and automate tasks using shell scripts. It provides a powerful and flexible environment for system administration, software development, and general-purpose computing.

Some popular Unix shells include:

1. Bourne Shell (sh): The original Unix shell, developed by Stephen Bourne.
2. Bash (Bourne Again SHell): A widely used shell that is compatible with the Bourne Shell but includes additional features and improvements.
3. C Shell (csh): Another popular Unix shell known for its C-like syntax.
4. Korn Shell (ksh): A shell that combines features from the Bourne Shell and C Shell, providing a powerful scripting language.
5. Zsh (Z Shell): An extended version of the Bourne Shell with additional features and customization options.

Each shell has its own set of features, syntax, and capabilities, but they all share the common goal of providing an interface for interacting with the Unix-like operating system.

## Find out which shell you are using

Use the echo command:

```shell
echo $SHELL
```

Output:

```
/bin/zsh
```

Use the ps command:

```shell
ps -p $$
```

Output:

```shell
  PID TTY           TIME CMD
18682 ttys003    0:00.47 /bin/zsh -il
```

## What is zsh?

Zsh, short for Z Shell, is an extended version of the Bourne Shell (sh) and is one of the most popular Unix shells available today. It was developed by Paul Falstad in 1990 and is designed to be an interactive and scripting shell with powerful features and customization options.

Here are some key features and characteristics of Zsh:

1. Command Completion: Zsh provides advanced command completion capabilities. It can automatically complete command names, file and directory names, and even arguments for many commands. It can also suggest completions based on previously entered commands or from a history of commands.

2. Advanced Prompt: Zsh allows extensive customization of the command prompt. Users can configure the prompt to display various information, such as the current directory, username, hostname, and more. It supports colors, formatting, and even dynamic prompts that change based on the context.

3. Extensibility: Zsh supports a wide range of plugins and extensions. It provides a modular framework called "oh-my-zsh," which allows users to easily install and manage plugins, themes, and configuration options. These extensions add additional features and improve productivity.

4. Improved Tabbing: Zsh offers enhanced tabbing functionality. Tabbing not only completes commands and filenames but also suggests options and switches for commands, making it easier to navigate and select the desired options.

5. Spelling Correction: Zsh includes a built-in spelling correction mechanism. If a command or a filename is mistyped, Zsh can suggest corrections or alternatives based on the closest matches. This feature helps to prevent errors and improves efficiency.

6. History Management: Zsh maintains a history of commands entered by the user, allowing easy retrieval and re-execution of previous commands. It supports searching, filtering, and navigation through command history, making it convenient to repeat or modify past commands.

7. Job Control: Zsh provides powerful job control capabilities. It allows users to manage and manipulate background processes, suspend and resume tasks, and switch between multiple tasks seamlessly.

Zsh offers many more features, such as file globbing, file name generation, arithmetic expansion, and more. It combines the best features of other shells, providing an interactive and efficient environment for both interactive usage and shell scripting.

### Explain ohmyzsh

Oh My Zsh is a community-driven framework for managing and customizing the Zsh shell. It was created by Robby Russell and is designed to enhance the Zsh experience by providing an extensive collection of plugins, themes, and configuration options.

Here are the key aspects of Oh My Zsh:

1. Easy Installation: Oh My Zsh simplifies the installation and setup process for Zsh. It can be installed with a single command, which automatically downloads and installs the necessary files. This makes it accessible for users who want to quickly enhance their Zsh environment.

2. Extensive Plugin System: Oh My Zsh offers a vast library of plugins that extend the functionality of Zsh. These plugins cover a wide range of features, such as auto-completion for specific commands, syntax highlighting, Git integration, Docker management, and much more. Users can easily enable or disable plugins to tailor their shell to their specific needs.

3. Customizable Themes: Oh My Zsh provides a variety of visually appealing and customizable themes for the Zsh prompt. These themes offer different layouts, colors, and information displayed in the prompt, allowing users to personalize their shell's appearance and display useful information, such as the current directory, time, Git branch, and more.

4. Configuration Options: Oh My Zsh allows users to customize various aspects of their Zsh configuration. It provides a central configuration file where users can set shell options, define aliases, and add custom functions. This makes it convenient for users to fine-tune their shell environment without dealing with complex configuration files manually.

5. Community-Driven Development: Oh My Zsh has a large and active community of contributors who continuously develop and improve the framework. The community maintains an extensive repository of plugins and themes, and users can easily contribute their own creations. This collaborative effort ensures that Oh My Zsh stays up-to-date with the latest features and provides a vibrant ecosystem for Zsh customization.

6. Simplified Management: Oh My Zsh includes built-in utilities for managing plugins, themes, and updates. Users can use simple commands to install, update, or remove plugins and themes, making it easy to maintain and expand their Zsh configuration.

Overall, Oh My Zsh enhances the Zsh shell experience by providing an easy-to-use framework for customization, extending functionality through plugins, and offering a visually appealing prompt with a wide range of themes. It has gained popularity among Zsh users for its simplicity, extensive community support, and the ability to tailor the shell to individual preferences and workflows.

### Install ohmyzsh

OhMyZsh can be installed from [here](https://ohmyz.sh/#install) or you can copy the command below.

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Package Managers

### Overview

Linux package managers are tools designed to handle the installation, management, and removal of software packages on Linux systems. They provide a convenient way to install and update software while resolving dependencies and ensuring system stability. Here are some key aspects and features of Linux package managers:

1. Repository-based: Linux package managers operate using software repositories, which are centralized servers that host software packages. These repositories contain pre-compiled packages for various software applications and libraries. Package managers fetch packages from these repositories to install on the system.

2. Dependency Resolution: Package managers handle dependencies automatically. When you install a package, the package manager checks for any other software components or libraries that the package relies on. It resolves and installs these dependencies, ensuring that all required components are present.

3. Package Installation: Package managers provide simple commands to install packages. You can specify the name of the package you want to install, and the package manager takes care of fetching it from the repository and installing it on your system.

4. Updates and Upgrades: Package managers offer mechanisms to keep your installed packages up to date. You can use commands like `update`, `upgrade`, or `dist-upgrade` to fetch the latest package information from the repositories and update or upgrade installed packages accordingly.

5. Package Removal: Package managers allow you to remove packages from your system, which also includes handling the removal of any associated dependencies that are no longer needed. This ensures clean and efficient package management.

6. Package Search and Information: Package managers provide commands to search for packages based on keywords, descriptions, or other criteria. You can also obtain detailed information about a specific package, such as its version, size, dependencies, and other relevant details.

7. Package Verification and Integrity: Package managers have built-in mechanisms to verify the integrity and authenticity of packages. This helps ensure that the packages are not tampered with or compromised during the download or installation process.

8. Package Manager Extensibility: Many package managers support extensions, plugins, or additional repositories, allowing users to access a wider range of software packages and customize their package manager's behavior.

Examples of popular Linux package managers include `apt` (Advanced Package Tool) used in Debian-based distributions like Ubuntu, `yum` (Yellowdog Updater, Modified) used in Red Hat-based distributions like CentOS and Fedora, `dnf` (Dandified Yum) which replaces `yum` in newer versions of Fedora, and `pacman` used in Arch Linux.

Linux package managers are fundamental tools in the Linux ecosystem, providing a streamlined and efficient way to manage software packages and maintain system stability and security.

### Homebrew

Homebrew is a popular package manager for macOS that simplifies the process of installing, managing, and updating software packages on your system. It provides a convenient command-line interface for handling software installations and dependencies.

Here are the key aspects and features of Homebrew:

1. Package Installation: Homebrew allows you to easily install a wide range of software packages and applications on your macOS system. With a simple command, you can install packages directly from the official Homebrew repository or tap into third-party repositories.

2. Dependency Management: Homebrew automatically handles dependencies when installing packages. It tracks and manages the dependencies required by a package, ensuring that all necessary libraries and components are installed correctly.

3. Package Versioning: Homebrew provides version management for packages. You can choose to install specific versions of a package, upgrade to the latest version, or switch between different versions as needed.

4. Updates and Upgrades: Homebrew makes it easy to keep your installed packages up to date. You can use the `brew update` command to update the Homebrew itself, and `brew upgrade` command to update all installed packages to their latest versions.

5. Formulae and Casks: Homebrew organizes software packages into formulae and casks. Formulae are used for command-line tools and libraries, while casks are used for graphical applications. This distinction allows you to install and manage different types of software more effectively.

6. Tap System: Homebrew provides a "tap" system that allows you to access additional repositories beyond the official Homebrew repository. These taps provide access to a broader range of packages maintained by the community or third-party developers.

7. Homebrew Bundle: Homebrew Bundle is a feature that allows you to define a list of packages in a `Brewfile`. This file can be version-controlled, shared, and easily installed on different systems, making it convenient to set up and replicate software environments.

8. Customizability: Homebrew is highly customizable, allowing you to configure options and settings for packages during installation. You can also customize the Homebrew installation itself, enabling or disabling specific features as desired.

Overall, Homebrew simplifies the process of managing software packages on macOS by providing a user-friendly command-line interface, handling dependencies, and offering a vast library of packages. It streamlines software installation, updates, and version management, making it a popular choice among macOS users and developers.

### Install homebrew

To install Homebrew on macOS, you can follow these steps:

1. Open a terminal application on your macOS system. You can find the terminal under the "Utilities" folder within the "Applications" directory.

2. In the terminal, paste the following command and press Enter:

   ```shell
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

   This command will initiate the installation process by downloading and executing the Homebrew installation script.

3. The installation script will prompt you to enter your password. Type your macOS user password and press Enter. Note that your password will not be visible as you type.

4. Wait for the installation to complete. The script will automatically download and install Homebrew on your system.

Once the installation is finished, you can start using Homebrew to install and manage software packages on your macOS system.

To verify that Homebrew is correctly installed, you can run the following command in the terminal:

```shell
brew --version
```

If Homebrew is installed properly, this command will display the version number of Homebrew installed on your system.

You can then begin using Homebrew to install packages by running commands like `brew install package_name`, where "package_name" represents the name of the package you want to install.

### Useful packages to start with

- brew install gnupg
- brew install httpie
- brew install jq

## Setting up the terminal

### Dot files

Dot files, also known as "hidden files," are files on Unix-like systems (including macOS and Linux) that have filenames starting with a dot (e.g., `.bashrc`, `.gitignore`). The dot prefix makes them hidden by default in file browsers and directory listings.

Dot files serve various purposes, including configuration, customization, and storing preferences for applications and the user's environment. Here are some common examples:

1. Shell Configuration: Dot files like `.bashrc`, `.zshrc`, or `.bash_profile` contain shell configuration settings. These files define environment variables, aliases, functions, and other customizations for the shell.

2. Text Editor Configuration: Text editors such as Vim and Emacs often use dot files like `.vimrc`, `.emacs`, or `.emacs.d/init.el` to store customization options, keybindings, and plugins.

3. Version Control: Version control systems like Git use dot files such as `.gitignore` to specify files or patterns to ignore when tracking changes in a repository.

4. Application Configuration: Some applications utilize dot files to store configuration settings. For instance, the MySQL database server uses `.my.cnf` to store login credentials and other configuration options.

5. Window Managers: Window managers and desktop environments may use dot files like `.xinitrc` or `.xprofile` to define startup commands, screen resolution settings, or desktop session configurations.

Dot files are typically located in the user's home directory (`~`). By default, these files are hidden from regular directory listings, but you can reveal them by using the `-a` option with the `ls` command (e.g., `ls -a`).

Editing or managing dot files can be done with any text editor or command-line tools. For example, you can edit `.bashrc` using a text editor like Vim, Nano, or a simple command-line editor like `nano ~/.bashrc`.

Dot files play a crucial role in customizing and configuring various aspects of a Unix-like system, allowing users to personalize their environment, define application settings, and streamline their workflows.

### What dot files are being used?

When logging into a Unix-like system, the specific dot files that are executed can vary depending on the shell and system configuration. Here are a few common dot files that may be run during the login process:

1. Shell Initialization Files:

   - Bash Shell: `.bash_profile`, `.bash_login`, `.profile`
   - Zsh Shell: `.zshrc`, `.zprofile`, `.zlogin`, `.zshlogin`
   - Other Shells: `.profile`

2. Environment Files:

   - Environment variables can be set in files like `.bashrc`, `.bash_profile`, `.profile`, `.zshrc`, etc.

3. Display Managers:

   - If you log in via a display manager (e.g., GDM, LightDM), it may execute certain dot files specific to the desktop environment, such as `.xprofile`.

4. Session Managers:
   - Some desktop environments use session managers (e.g., GNOME's `gnome-session`) that may execute additional dot files or scripts to set up the session environment.

To determine which dot files are being run during the login process, you can follow these steps:

1. Open a terminal on your Unix-like system.

2. Run the appropriate command to identify the shell you are using:

   - For Bash: `echo $SHELL`
   - For Zsh: `echo $ZSH_NAME`
   - For other shells: Consult the documentation or use a similar command specific to your shell.

3. Based on the output of the command in step 2, identify the shell initialization files associated with your shell.

4. Open each identified file using a text editor (e.g., `nano`, `vim`) to view its contents. Look for any commands or references to other dot files that are sourced or executed during the login process.

Note that the precise order and files executed can depend on the specific shell, operating system, and user configuration. Also, different shells have different conventions and priorities for the initialization files they execute.

By examining the shell's documentation and inspecting the relevant dot files, you can gain insight into which dot files are executed when logging into your Unix-like system.

### Customise dot files

#### Aliases

In Linux, an alias is a user-defined shortcut or alternate name for a command or series of commands. It allows you to create a new name for an existing command or define a sequence of commands that can be executed by typing a shorter, more memorable alias instead of the complete command.

Aliases can be helpful for saving time and reducing the need to type long or complex commands frequently. They can also be used to customize and personalize your command-line experience. Here are a few key points about Linux aliases:

1. Syntax: An alias is typically defined in the shell's configuration file (e.g., `.bashrc`, `.zshrc`) or in a separate file that is sourced by the shell. The general syntax for creating an alias is as follows:

   ```shell
   alias alias_name='command'
   ```

2. Command Substitution: The `command` part of the alias can be a single command or a sequence of commands enclosed in quotes. You can use command substitution (using backticks or `$(...)`) within the alias definition to include dynamic values or execute complex commands.

3. Persistency: Aliases are usually defined in the shell's configuration file to ensure that they are available every time you start a new shell session. Changes to the configuration file require a shell restart or reloading the file to take effect.

4. Overriding: If you define an alias that has the same name as an existing command, the alias will take precedence when you use that name in the shell. However, the original command can still be accessed by specifying its full path or using a backslash (`\`) before the command name.

5. Listing Aliases: To list all defined aliases in your current shell session, you can use the `alias` command without any arguments. It will display a list of defined aliases and their corresponding commands.

Here's an example that demonstrates how to create an alias:

```shell
alias ll='ls -alh'
```

In this example, the alias `ll` is created for the `ls -alh` command. Now, whenever you type `ll` in the terminal, it will execute the equivalent `ls -alh` command.

It's important to note that aliases are specific to the shell you are using (e.g., Bash, Zsh). Different shells may have slightly different syntax or behavior for defining and using aliases.

Overall, aliases are a convenient way to create shortcuts and streamline your command-line experience in Linux. They allow you to define custom commands or simplify the usage of existing commands by assigning them a shorter, more memorable name.

#### Functions

In Linux, a function is a named block of code that performs a specific task or set of tasks. Functions allow you to group a series of commands together, provide parameters for customization, and enable code reuse. They are commonly used in shell scripts but can also be defined and used directly in an interactive shell session. Here are some key points about Linux functions:

1. Function Definition: A function is defined using the following syntax:

   ```shell
   function_name() {
       # commands
   }
   ```

   You can also use the `function` keyword before the function name, but it is optional in most modern shells.

2. Parameters: Functions can accept parameters (arguments) that provide data or values to the function. Parameters are accessed within the function using special variables, such as `$1`, `$2`, and so on, representing the first, second, and subsequent parameters, respectively.

3. Local Variables: Functions can define local variables that are only accessible within the function's scope. Local variables are declared using the `local` keyword before the variable name.

4. Return Value: Functions can return a value using the `return` statement. The returned value can be accessed using the special variable `$?` after the function call.

5. Function Invocation: To execute a function, you simply call it by name, followed by any necessary arguments. For example:

   ```shell
   function_name argument1 argument2
   ```

6. Code Reusability: Functions provide a way to encapsulate a set of commands into a single unit, allowing for code reuse and modularity. Instead of duplicating code, you can call a function whenever you need to perform a specific task.

Here's an example that demonstrates how to define and use a function in a shell script:

```shell
# Function definition
print_greeting() {
    local name=$1
    echo "Hello, $name!"
}

# Function invocation
print_greeting "John"
```

In this example, the `print_greeting` function is defined with a single parameter `name`. It prints a greeting message with the provided name. The function is then invoked with the argument `"John"`, resulting in the output: "Hello, John!"

Functions are particularly useful in shell scripting to modularize code, improve readability, and enable code reuse. They allow you to define custom actions or operations and execute them with different arguments or in various parts of your script.

## Useful builtin commands

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

## echo

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

## eval

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

## env

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

## history

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

## sudo

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

## ls

## cd

## dir

## mkdir

## touch

## chmod

## chown

## cp

## df

## du

## grep

## find

## lsof

## ps

## pwd

## cat

## tail

## which

## rm
