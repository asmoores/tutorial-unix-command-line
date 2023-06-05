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

### Explain dot files

Figure out which init file the shell is using

Enable history and searching

Edit .profile

    Add an alias
    Add a function

## man

## echo

## eval

## env

## history

## sudo

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
