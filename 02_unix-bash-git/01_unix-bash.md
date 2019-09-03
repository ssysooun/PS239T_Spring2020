
# Navigating Operating Systems 

> ### Learning objectives
> 
> * Explain the difference between command line and GUI methods of interacting with computers
> * Explain when and why command-line interfaces should be used instead of graphical interfaces.
> * Explain how shell programs are used to interact with computers using a command line. 
> * Explain why Unix shells like Bash are pre-installed on Mac but not Windows computers. 
> * Discuss how using Unix shell is different on Mac and Windows OS. 


## 1. What is an Operating System? 

An operating system (OS) is a suite of programs which make the computer work. It is a stable, multi-user, multi-tasking system for servers, desktops and laptops. Most personal computers use Mac, Windows, or Linux OS.


## 2. Human-Computer Interfaces

We navigate our operating systems and tell our computers to do things using human-computer interfaces. 

### Two common human-computer interfaces

#### GUI 

Most people interact with their computers using **Graphical User Interfaces (GUIs)**. A GUI (pronounced gooey) is a way of interacting with your computer through graphical icons and visual indicators, typically using a mouse. 

#### Command Line (CLI)

**Command-line Interface (CLI)** is a method of interacting with your computer through typing commands. CLI only uses keyboard input (and not mouse input). 

You may hear the term 'read-evaluate-print loop' (or REPL) used to describe command-line interface. The 'read-evaluate-print loop' is a simple concept at the heart of CLI. Simply put, when the user types a command and then presses the enter (or return) key, the computer reads it, executes it, and prints its output. The user then types another command, and so on until the user logs off.

### Why use a command-line interface?

William Shotts the author of *[The Linux Command Line](http://linuxcommand.org/tlcl.php)* summarized the promise and challenges of CLI when he stated,  
> graphical user interfaces make easy tasks easy, while command line interfaces make difficult tasks possible.

Practically, you should learn it because... 

1. You will be using it at the beginning of every class.
	* You will use two(ish) commands in the shell before every class to copy an updated version of the course materials onto your computer. 
	* You will be expected to follow along and do in-class exercises using the files on GitHub. 
	* The material for this class is not fixed. It will be updated periodically. 

2. For certain tasks, it can make your life a lot easier. 
	* Manipulating large data files 
	* Renaming and reorganizing files 
	* Moving and running files on an external server 


## 3. Where is this command line? 

We use shell programs to interact with our computers using a command line. 

Although there are many shell programs available, we will be focusing on Bash. 


## 4. What is a (command line) shell? 

A shell is an old-school way of interacting with your computer (but also new-school because serious programmers use it all the time). 

Because this class focuses on applying computer skills rather than underlying theory, I won't be giving you a detailed description of how a shell works. 

### A note about vocabulary... 

In addition to shell and command line, you may also hear the term 'terminal' used to describe using a command line to interact with your computer. 

### Why learn to use a shell? 

1. You will be using it at the beginning of every class.

* You will use two(ish) commands in the shell before every class to copy an updated version of the course materials onto your computer. 
* You will be expected to follow along and do in-class exercises using the files on GitHub. 
* The material for this class is not fixed. It will be updated periodically. 

2. For certain tasks, it can make your life a lot easier. 

* Manipulating large data files 
* Renaming and reorganizing files 
* Moving and running files on an external server 


## Bash 

Bash is the most common Unix shells. Like R, 'Bash' is a program as well as a language. In other words, we run bash commands using the bash program. 

Bash stands for the Bourne Again Shell (so-called because it's derived from a shell written by Stephen Bourne --- this is what passes for wit among programmers). Bash is the default shell on most modern implementations of Unix, and in most packages that provide Unix-like tools for Windows.


### Why did we download a bash shell on Windows but not Mac computers? 

In this course, we will be using a Unix shell. Unix and Unix-like operating systems have this shell built-in. Mac OS (OSX) is a version of Unix. Similarly, Linux is Unix-like and also has the shell built-in. 

Windows was designed seperately from Unix. Thus, it does not have Bash built-in. This is one of many differences between Windows and Unix. 


## Unix vs. Windows 

Unix has several fundamental differences compared with Windows:

* More rigorous security
* Extremely powerful command-line tools 
* Very stable
* Entirely different directory structure

For our purposes, most differences between Unix and Windows aren't relevant. 

One exception are the file structures. Practically, Windows users will need to change "\" to "/". 
* The Windows File Explorer seperates subdirectories and files using backslashes ("\"). 
* When you write file paths in the bash shell, use a frontslash ("/") to seperate subdirectories and files.  

See below for more information about Unix and the file structure. 


******************************************

## Additional Reference Information

### More Unix Background 

UNIX is an operating system which was first developed by AT & T employees at Bell Labs (1969-1971).  Bell Labs canceled the project (MULTICS) but was continued by the employees worked in a smaller scale. The new project was named UNICS (Uniplexed Information and Computation System) and then renamed UNIX. Due to [the anti-trust issue](https://en.wikipedia.org/wiki/Breakup_of_the_Bell_System), AT & T gave away UNIX in 1975. Berkeley is one of the main places where UNIX was developed. [The Berkeley Software Distribution](https://en.wikipedia.org/wiki/Berkeley_Software_Distribution), one of the branches of UNIX, came out it 1977.

From Mac OS X to Linux, many of current operation systems are some versions of UNIX. 

For more information on the history of UNIX, see [this link](https://docs.google.com/presentation/d/1kKt9V6rom55hU6SJ2_3nGluobjtScptlnJV9YFe6Jz4/pub?start=false&loop=false&delayms=3000&slide=id.g163c5ae2ce_0_17).

![Unix history](https://upload.wikimedia.org/wikipedia/commons/thumb/7/77/Unix_history-simple.svg/1200px-Unix_history-simple.svg.png)

### Key Components of Unix 

(Adapted from [Indiana University](https://kb.iu.edu/d/agat))

Unix has three main components

#### Kernel

The kernel of UNIX is the hub of the operating system: it allocates time and memory to programs and handles the [filestore](http://users.ox.ac.uk/~martinw/unix/chap3.html) (e.g., files and directories) and communications in response to system calls. 

#### Shell

The shell is an interactive program that provides an interface between the user and the kernel. The shell interprets commands entered by the user or supplied by a shell script, and passes them to the kernel for execution. 

As an illustration of the way that the shell and the kernel work together, suppose a user types `rm myfile` (which has the effect of removing the file *myfile*). The shell searches the filestore for the file containing the program `rm`, and then requests the kernel, through system calls, to execute the program `rm` on *myfile*. When the process `rm myfile` has finished running, the shell then returns the UNIX prompt % to the user, indicating that it is waiting for further commands.

We'll talk more about shells in a little bit.

#### File system

Unix and Unix-like operating systems employ a hierarchical (i.e., inverted tree) directory structure, with the root directory (/) at the top. 

The standard file system has, among others, the following directories:

| Directory | Description |
| --------- | ----------- |
| /  | The root directory, where the whole tree starts |
| /bin  | Contains fundamental executables (i.e., binaries) generally used by all users on the system (e.g., chmod, cp, mv, grep, and tar) |
| /etc | Contains local configuration files, subdirectories containing configuration files for large software packages (e.g., the X11 window system) |
| /lib  | Contains shared libraries needed to boot the system and run the commands in the root file system |
| /tmp  | Local scratch space for storing temporary files, which may be deleted without notice |
| /usr/bin | The primary directory for most executables used by normal users on the system (e.g., emacs, make, scp, sftp, ssh, and yum) |
| usr/lib |Contains static and dynamic libraries, a few executables that usually are not invoked directly, and subdirectories for complex program |













