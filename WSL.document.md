# WSL Overview: 
* As a developer, you will need to access specific coding tools, languages, and frameworks. You may want to install Python and a web development framework like Django, work with JavaScript on a NodeJS backend, or install a cross-platform project that uses React. 
* These programming languages will work on all operating systems. But there are many scenarios that may prefer one operating system to another. Building Windows native desktop apps works best using Windows. Building a web app that will be deployed to a custom Linux server or production-ready Linux Virtual Machine (VM) works best using a Linux environment. 
* Throughout the day, we need to use email and Outlook, create Word docs, Excel spreadsheets, and PowerPoint presentations, and then need to jump on an online call. 
* Rather than using separate machines to handle these needs, some developers choose to dual-boot or run virtual machines (VMs). 
* **Dual-boot**: In the past, running both Windows and Linux on one machine required you to install both operating systems separately and use a boot manager to choose which would run your computer during startup. There are some problems with this, like you need to restart your machine every time you wanted to switch between systems.
* **Virtual Machine**: Virtual Machines (VM) are one way to address the issued of dual-booting two different operating systems. VMs enable you to run a virtualized instance of Linux on a device running Windows. The problem with VMs are slower performance due to the amount of resources that need to be allocated to the running virtual instance, also lack of integration between the two operating systems as you're still running isolated separate systems. 
* **WSL**: WSL addresses these issues by integrating Windows and Linux with a much smaller resource footprint, requiring fewer resources (CPU, memory, storage) compared to traditional Virtual Machines. Windows Subsystem for Linux (WSL) lets developers run a GNU/Linux environment including most command-line tools, utilities, and applications, directly on Windows, unmodified, without the overhead of a traditional virtual machine or dual-boot setup. 
* **WSL advantages over VM**: 
  - It is very much faster to launch a WSL terminal than start up a VM. 
  - much lesser memory requirement than a virtual machine. 
  - integration with windows is much easier with WSL.

* **Common scenarios for using WSL**: A few common situations or scenarios where a developer may want to use WSL include: 
  - A beginner who wants to learn coding on both Windows and Linux environments.
  - A professional developer who wants access to Linux and Windows tools.
  - Any organization that wants to operationalize a Continuous Integration and Continuous Delivery (CICD) workflow, testing updates on a local machine before deploying code updates to the cloud.
  - Anyone who wants to use Docker for creating containers, Git for version control, GPU acceleration for Machine Learning, databases (like MySQL, PostgreSQL, MongoDB, Redis, SQLite), or have access to both Linux GUI apps and Windows at the same time. 

* There are two WSL versions are available i.e. WSL1 and WSL2. The comparison between two is shown in following table. 
    <img src="compare.png" width="600" /> 
      &nbsp;<br>


# WSL Installation Steps 
* **Step 1**: Check whether virtualization is enabled in your system. To check this open "Task Manager". Navigate to "Performances" tab. At bottom look for virtualization. If it is enabled then fine, you may proceed to WSL installation. But if it is disabled, you need to enable it in BIOS settings. To do so you may follow this article : https://www.simplilearn.com/enable-virtualization-windows-10-article.
   <img src="task.png" width="600" /> 
      &nbsp;<br>
* **Step 2**: If virtaualization is enabled, then go to search and search for "Turn windows features on or off". It will open a window. In that enable options "Virtual machine platform", "Windows Hyperviser platform" and "windows subsystem for linux". 
    <img src="wsl1.png" width="600" /> 
      &nbsp;<br> 

* **Step 3**: Check for windows version and build. You must be running windows 10 or later & version & build requirements are : Version 2004 or later, with Build 19041 or later. To check press "windows key + R" and type "winver" there and press enter. 
* **Step 4**: If your windows fullfills above requirement, open windows powershell as "administrator" and run command `wsl --install`.
* **Step 5**: Next we need to install linux distribution. To see all available linux distributions, run command `wsl --list --online` or `wsl -l -o`. Then install your favourite distribution using command `wsl --install -d <distribution name>`. During installation, you need to configure your linux distribution by providing username & password. To check running distributions & their versions use command `wsl --list --verbose`. You can also install linux distribution directly from microsoft store.  


# Linux Commands
* Linux commands are divided into followining sections: 
  1. Linux Directory Commands: 
     - pwd Command: The pwd command is used to display the location of the current working directory. Syntax: `pwd`
     - mkdir Command: This is used to create a new directory under any directory. Syntax: `mkdir <directory name>`
     - ls Command: This is used to display a list of content of a directory. Syntax: `ls`
     - cd Command: The cd command is used to change the current directory. Syntax: `cd <directory name>`
     - rmdir Command: The rmdir command is used to delete an empty directory. `rmdir <directory name>`
     - rm -r Command: This command is used to delete a directory with the files & directories it contains. Syntax: `rm -r <directory name>`

  2. Linux File Commands: 
     - touch Command: The touch command is used to create empty files. We can create multiple empty files by executing it once. Syntax: `touch <filename>`. For multiple files: `touch <file1> <file2>`
     - cat Command: The cat command is a multi-purpose utility in the Linux system. It can be used to create a file, display content of the file, copy the content of one file to another file, etc. 
     Syntax: 
      a. To display content: `cat <filename>`
      b. To create a file: `cat > <filename>` You may enter text or code right here & then press "ctrl + d" to come out of it.
      c. To copy content of one file to another: `cat <file1> > <file2>` 
    
      - rm Command: The rm command is used to remove a file. Syntax: `rm <file name>` 
      - cp Command: The cp command is used to copy a file or directory Syntax: 
        a. To copy in same directory: `cp <existing filename> <new filename>` 
        b. To copy in a different directory: `cp <existing filename> <directory name>` 

      - mv Command: The mv command is used to move a file or a directory form one location to another location. Also it can be used to rename a file.
      Syntax: 
      a. To move file or directory: `mv <file or directory name> <directory path>`   
      b. To rename a file: `mv <old filename> <new filename>`
  3. Linux File Content Commands 
      - head Command: The head command is used to display the content of a file. It displays the first 10 lines of a file. Syntax: `head <file name>`  
      - tail Command: It displays the last ten lines of the file content. Syntax: `tail <file name>` 
      - tac Command: The tac command is the reverse of cat command, as its name specified. It displays the file content in reverse order (from the last line). Syntax: `tac <file name>`

  4. Linux User Commands: 
      - su Command: The su command provides administrative access to another user. In other words, it allows access of the Linux shell to another user. Syntax: `su <user name>` 
      - id Command: The id command is used to display the user ID (UID) and group ID (GID). Syntax: `id`
      - useradd Command: The useradd command is used to add or remove a user on a Linux server. Syntax: `sudo useradd <username>` 
      - passwd Command: The passwd command is used to create and change the password for a user. Syntax: `sudo passwd <username>` 
      - groupadd Command: The groupadd command is used to create a user group. Syntax: `groupadd <group name>` 

  5. Linux Filter Commands:
     - cut Command: The cut command is used to select a specific column of a file. The '-d' option is used as a delimiter, and it can be a space (' '), a slash (/), a hyphen (-), or anything else. And, the '-f' option is used to specify a column number. Syntax: `cut -d(delimiter) -f(columnNumber) <fileName>`  
     - grep Command: The grep is the most powerful and used filter in a Linux system. The 'grep' stands for "global regular expression print." It is useful for searching the content from a file. Generally, it is used with the pipe. Syntax: `command | grep <searchWord>` 
     - sort Command: The sort command is used to sort files in alphabetical order. Syntax: `sort <file name>`
     - gzip Command: The gzip command is used to truncate the file size. It is a compressing tool. It replaces the original file by the compressed file having '.gz' extension. Syntax: `gzip <filename>`
     - gunzip Command: The gunzip command is used to decompress a file. It is a reverse operation of gzip command. Syntax: `gunzip <file1>`

  6. Linux Utility Commands: 
     - find Command: The find command is used to find a particular file within a directory. It also supports various options to find a file such as byname, by type, by date, and more. Syntax: `find . -name "<filename>"` 
     - locate Command: The locate command is used to search a file by file name. It is similar to find command; the difference is that it is a background process. It searches the file in the database, whereas the find command searches in the file system. It is faster than the find command. Syntax: `locate <file name>` 
     - date Command: The date command is used to display date, time, time zone, and more. Syntax: `date`
     - cal Command: The cal command is used to display the current month's calendar with the current date highlighted. Syntax: `cal` 
     - exit Command: Linux exit command is used to exit from the current shell. It takes a parameter as a number and exits the shell with a return of status number. Syntax: `exit`
     - clear Command: Linux clear command is used to clear the terminal screen. Syntax: `clear`        

  7. Linux Networking Commands:
     - ip Command: Linux ip command is an updated version of the ipconfig command. It is used to assign an IP address. Syntax: `ip a` or `ip addr`  
     - ping Command: The ping command is used to check the connectivity between two nodes, that is whether the server is connected. It is a short form of "Packet Internet Groper." Syntax: `ping <destination>` 
     - host Command: The host command is used to display the IP address for a given domain name and vice versa. It performs the DNS lookups for the DNS Query. Syntax: `host <domain name>`or `host <ip address>`    