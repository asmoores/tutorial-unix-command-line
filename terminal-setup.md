# Setting up the terminal

## Dot files

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

## What dot files are being used?

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

## Customise dot files

### Aliases

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

### Functions

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