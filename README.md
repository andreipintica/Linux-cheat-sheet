Bash is the Unix command-line interface (CLI). Also called the terminal, the command line, or the shell. It's a command language that allows us to work with files on our computers in a way that's far more efficient and powerful than using a GUI (graphical user interface).

🔧 Technologies & Tools

<img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=blue" height=21 width=80>
 <img src="https://badges.frapsoft.com/bash/v1/bash.png?v=103)](https://github.com/ellerbrock/open-source-badges">
 <img src="https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white" height=22 width=110>
<br>
<br>

> Click :star:if you like the project. Follow me [@AndreiPintica](https://www.linkedin.com/in/andreipintica/) for technical updates.


### Table of Contents

---

| No. | Topic                                                                   |
| --- | ----------------------------------------------------------------------- |
| 1   | [**Networking**](#networking)                                           |
| 2   | [**Users and groups**](#users-and-groups)                               |
| 3   | [**File commands**](#file-commands)                                     |
| 4   | [**Directory navigation**](#directory-navigation)                       |
| 5   | [**Hardware information**](#hardware-information)                       |
| 6   | [**File compression**](#file-compression)                               |
| 7   | [**Package installation**](#package-installation)                       |
| 8   | [**System management**](#system-management)                             |
| 9   | [**File permission**](#file-permission)                                 |
| 10  | [**SSH**](#ssh)                                                         |
| 11  | [**Variables**](#variables)                                             |
| 12  | [**File transfer**](#file-transfer)                                     |
| 13  | [**Disk usage**](#disk-usage)                                           |
| 14  | [**Process related**](#process-related)                                 |
| 15  | [**Shell command**](#shell-command)                                     |
| 16  | [**Searching**](#searching)                                             |

### Networking

1.  **Display network information:** `ifconfig` command is used to display all network information(ip address, ports etc)

    ```bash
    ifconfig -a
    ```

2.  **Check network status:** Send multiple ping requests using the ICMP protocol.

    ```bash
    ping <ip-address> or <hostname>

    Example:
    ping 10.0.0.1
    ```

3.  **Show IP Address:** Display ip address of a current machine.

    ```bash
    hostname -I
    ```

4.  **Active ports:** Shows active or listening ports

     ```bash
     netstat -pnltu
     ```

5.  **Find information about domain:** `whois` command is used to find out information about a domain, such as the owner of the domain, the owner’s contact information, and the nameservers used by domain.

    ```bash
    whois [domain]

    Example:
    whois bing.com
    ```
6.  **IP address reverse lookup**
    ```bash
    dig -x <ip-address>
    ```
7.  **Domain reverse lookup**
    ```bash
    dig -x <hostname>
    ```
8.  **Show domain's DNS info**
    ```bash
    dig <domain>
    ```
9.  **Download a file from url**
    ```bash
    get <file>
    
    Example:
    get https://example.com/file.txt
    ```
10. **HTTP requests**
    ```bash
    curl https://example.com                               # Return response body
    curl -i|--include https://example.com                  # Include status code and HTTP headers
    curl -L|--location https://example.com                 # Follow redirects
    curl -O|--remote-name foo.txt https://example.com      # Output to a text file
    curl -H|--header "User-Agent: Foo" https://example.com # Add a HTTP header
    curl -X|--request POST -H "Content-Type: application/json" -d|--data '{"foo":"bar"}' https://example.com # POST JSON
    curl -X POST -H --data-urlencode foo="bar" http://example.com  # POST URL Form Encoded
    ```
11. **Show IP addresses**
    ```bash
    ip addr show
    ```
12. **Assign IP address to interface**
    ```bash
    ip address add <ip>
    ```
13. **Show domain information**
    ```bash
    nslookup <domain>
    
    Example:
    nslookup bing.com
    ```
14. **Upload file from local to remote computer**
    ```bash
    put <file>
    ```
15. **Download a file from url**
    ```bash
    wget https://example.com/file.txt                              # Download a file to the current directory
    wget -O|--output-document example.txt https://example.com/file.txt # Output to a file with the specified name
    ```


**[⬆ Back to Top](#networking)**

### Users and groups

1.  **Add a new user**
    ```bash
    adduser <user>
    ```
2.  **Change directory group:** Used to change group ownership for file.

    ```bash
    chgrp <group> <filename>

    Example:
    sudo chgrp Administrator sample.txt
    ```
3.  **Add a new user group**
    ```bash
    groupadd <group>
    ```
4.  **Show user and group information for a specified user.**
    ```bash
    id
    ```
5.  **Display all the groups for which the user belongs to.**
    ```bash
    group
    ```



6. **Shows a list of recent logins on the system by fetching data from /var/log/wtmp file.**
    ```bash
    last 

    Example:

    last
    azadmin      :0           :0               Fri Aug 28 01:27    gone - no logout
    reboot   system boot  5.4.0-29-generic Fri Aug 28 01:27   still running
    azadmin      :0           :0               Wed Jul 29 11:46 - crash (29+13:40)
    reboot   system boot  5.4.0-29-generic Wed Jul 29 11:45   still running
    azadmin      :0           :0               Thu May 14 21:04 - crash (75+14:41)
    reboot   system boot  5.4.0-29-generic Thu May 14 21:03   still running

    wtmp begins Thu May 14 21:03:56 2020
    ```
7.  **Show recent login of all users or of a given user**
    ```bash
    lastlog

    Example:
    Username         Port     From             Latest
    daemon                                     **Never logged in**
    bin                                        **Never logged in**
    sys                                        **Never logged in**
    sync                                       **Never logged in**
    games                                      **Never logged in**
    man                                        **Never logged in**
    lp                                         **Never logged in**
    mail                                       **Never logged in**
    news                                       **Never logged in**
    ```
8. **Change user password**
    ```bash
    passwd <username>
    ```
9. **Delete a user**
    ```bash
    userdel <username>
    ```
10. **Modify a user account**
    ```bash
    usermod
    ```
11. **Add a user to a group**
    ```bash
    usermod -aG <group> <user>
    ```
12. **Show logged users and activity**
    ```bash
    w
    ```
13. **Show who is loged in**
    ```bash
    who
    ```
14. **Check user exist or not**
    ```bash
    import pwd

    def user_chk(user):
    try:
        pwd.getpwnam(user).pw_name == user
        return f'User {user!r} exist.'
    except KeyError:
        return f'User {user!r} not exist.'
    print(user_chk(input('Enter User Name: ')))
    ```

**[⬆ Back to Top](#users-and-groups)**


### File commands

1.  **Print lines matching a pattern**
    ```bash
    awk '<pattern> {print $0}' <file>
    ```
2.  **Creating files**
    ```bash
    touch foo.txt          # Create file or update existing files modified timestamp
    touch foo.txt bar.txt  # Create multiple files
    touch {foo,bar}.txt    # Create multiple files
    touch test{1..3}       # Create test1, test2 and test3 files
    touch test{a..c}       # Create testa, testb and testc files
    mktemp                 # Create a temporary file
    ```
3.  **Copy file1 to file2**
    ```bash
    cp <file1> <file2>
    ```
4.  **Copy directory1 to directory2**
    ```bash
    cp -r <directory1> <directory2>
    ```
5.  **Cut file section and print**
    ```bash
    cut -d <delimiter> <file>       
6.  **Compare two files**
    ```bash
    diff <file1> <file2>
    ```
7.  **Decrypt a file**
    ```bash
    gpg <file>
8.  **Encrypt a file**
    ```bash
    gpg -c <file>
    ```
9.  **Show first 10 lines of a file**
    ```bash
    head <file>
    ```
10. **Present text and allows scrolling beyond**
    ```bash
    less
    ```
11. **Create symbolic link to a file**
    ```bash
    ln -s</path/file><link>
    ln -s|--symbolic foo bar            # Create a link 'bar' to the 'foo' folder
    ln -s|--symbolic -f|--force foo bar # Overwrite an existing symbolic link'bar'
    ls -l                               # Show where symbolic links are pointing
    ```
12. **List files in the directory**
    ```bash
    ls
    ls | xargs wc             # Words/lines/bytes in directory
    ls -a|--all               # List directories including hidden
    ls -l                     # List directories in long form
    ls -l -h|--human-readable # List directories in long form with human readable sizes
    ls -t                     # List directories by modification time, newest first
    ```
13. **Create a directory**
    ```bash
    mkdir <foldername>
    ```
14. **Show file contents**
    ```bash
    more <file>
    ```
15. **Rename a file**
    ```bash
    mv <filename1> <filename2>
    ```
16. **Show current directory**
    ```bash
    pwd
    ```
17. **Deleting files and directories**
    ```bash
    rm <file>
    rmdir foo                        # Delete empty directory
    rm -r|--recursive foo            # Delete directory including contents
    rm -r|--recursive -f|--force foo # Delete directory including contents, ignore nonexistent files and never prompt
    rm -rf <directory>               # Force remove directory
    ```
18. **Overwrite and delete a file**
    ```bash
    shred -u <file>
    ```
19. **Compile from source code**
    ```bash
    source <file>
    ```
20. **Run commands/programs with root permission(administrator)**
    ```bash
    sudo
    ```
21. **Show last 10 lines of a file**
    ```bash
    tail <file>
    ```
22. **Count words/lines/bytes**
    ```bash
    wc
    ```
23. **Store command output to a file - skip terminal output**
    ```bash
    <command> | tee <file> >/dev/null
    ```
24. **Cut data section and print**
    ```bash
    <data> | cut -d <delimiter>
    ```

**[⬆ Back to Top](#file-commands)**

### Directory navigation

1.  **Move up one level**
    ```bash
    cd
    ```
2.  **Change to a specified directory**
    ```bash
    cd </directory>
    ```
3.  **Change to home directory**
    ```bash
    cd ~
    ```
4.  **Go to test sub directory**
    ```bash
    cd test
    ```
5.  **Go to last directory**
    ```bash
    cd -
    ```

**[⬆ Back to Top](#directory-navigation)**

### Hardware information

1.  **Show CPU information**
    ```bash
    cat /proc/cpuinfo
    ```
2.  **Show bootup messages**
    ```bash
    dmesg
    ```
3.  **Show BIOS hardware info**
    ```bash
    dmidecode
    ```
4.  **Show free and used memory**
    ```bash
    free -h
    ```
5.  **Block devices info**
    ```bash
    lsblk
    ```
6.  **Hardware configuration info**
    ```bash
    lshw
    ```
7.  **Tree-diagram of PCI devices**
    ```bash
    lspci -tv
    ```
8.  **Tree-diagram of USB devices**
    ```bash
    lsusb -tv
    ```
9.  **Display OS and hardware info**
    ```bash
    neofetch
    ```
10. **Show disk data info**
    ```bash
    hdparm -i /dev/<disk>
    ```
11. **Disk read speed test**
    ```bash
    hdparm -tT /dev/<disk>
    ```
12. **Unreadable blocks test**
    ```bash
    badblocks -s /dev/<disk>
    ```

**[⬆ Back to Top](#hardware-information)**

### File compression

1.  **Create a gz compressed file**
    ```bash
    gzip <file>
    ```
2.  **Extract archived file**
    ```bash
    tar xf <file.tar>
    ```
3.  **Package and compress files**
    ```bash
    zip
    unzip
    ```
4.  **Create a tar file from a file**
    ```bash
    tar cf <file.tar> <file>
    ```
5.  **Create a gzfiple tar file**
    ```bash
    tar czf <file.tar.gz>
    ```
**[⬆ Back to Top](#file-compression)**

### Package installation 

1.  **Search for and install software packages**
    ```bash
    apt-get
    ```
2.  **Install a package with APT**
    ```bash
    apt install <package>
    ```
3.  **Install a package with DNF**
    ```bash
    dnf install <package.rpm>
    ```
4.  **Remove an RPM package**
    ```bash
    rpm -e <package.rpm>
    ```
5.  **Install a local rpm package**
    ```bash
    rpm -i <package.rpm>
    ```
6.  **Package info and summary**
    ```bash
    yum info <package>
    ```
7.  **Install a package with YUM**
    ```bash
    yum install <package.rpm>
    ```
8.  **Find a package by a keyword**
    ```bash
    yum search <keyword>
    ```
9.  **Install software from source code**
    ```bash
    tar zxvf <source_code.tar.gz>
    cd <source_code>
    ./configure
    make
    make install
    ```
**[⬆ Back to Top](#package-installation)**

### System management

1.  **Show current day and month**
    ```bash
    cal
    ```
2.  **Show current time and date**
    ```bash
    date
    ```
3.  **Show user information**
    ```bash
    finger <username>
    ```
4.  **Show system hostname**
    ```bash
    hostname
    ```
5.  **Show system IP address**
    ```bash
    hostname -l
    ```
6.  **Show reboot history**
    ```bash
    last reboot
    ```
7.  **Add a new kernel module**
    ```bash
    modprobe <modulename>
    ```
8.  **System shutdown and reboot**
    ```bash
    shutdown <hh:mm>             # Schedule a system shutdown
    shutdown                     # Shutdown in 1 minute
    shutdown now                 # Immediately shut down
    shutdown +5                  # Shutdown in 5 minutes
    shutdown -r|--reboot         # Reboot in 1 minute
    shutdown -r|--reboot now     # Immediately reboot
    shutdown -r|--reboot +5      # Reboot in 5 minutes
    shutdown -c                  # Cancel a shutdown or reboot
    reboot                       # Reboot now
    reboot -f                    # Force a reboot
    ```
9.  **Manage the system clock**
    ```bash
    timedatectl
    ```
10. **View or limit system resources**
    ```bash
    ulimit <flags> <limit>
    ```
11. **System and hardware information**
    ```bash
    uname -a                    # Print all information 
    uname -s                    # Print kernel name
    uname -r                    # Print kernel release
    uname -m                    # Print arhitecture
    uname -o                    # Print operating system
    ```
12. **Show uptime length/avg load**
    ```bash
    uptime
    ```
13. **Show the current user** 
    ```bash
    whoami
    ```
**[⬆ Back to Top](#system-management)**

### File permission

1.  **Full permission to owner, read permissions for others**
    ```bash
    chmod 755 <file>
    ```
2.  **Full permission to owner, read and write for others**
    ```bash
    chmod 766 <file>
    ```
3.  **File read, write, execute permissions to everyone**
    ```bash
    chmod 777 <file>
    ```
4.  **Change file ownership**
    ```bash
    chown <user> <file>
    ```
5.  **Change fle owner and group**
    ```bash
    chown <user>:<group> <file>
    ```

**[⬆ Back to Top](#file-permission)**

### SSH

1.  **Connect to host as user**
    ```bash
    ssh <user>@<host>
    ```
2.  **Connect to host via port 22**
    ```bash
    ssh <host>
    ```
3.  **Connect to host using IP address**
    ```bash
    ssh <ip address>
    ```
4.  **Connect using custom port**
    ```bash
    ssh <hostname> or <ip address> -p <port number>
    ```
5.  **Connect to host using the identity file**
    ```bash
    ssh -i test.pem <hostname> or <ip address>
    ```
6.  **Generate SSH keys using keygen**
    ```bash
    ssh-keygen -t rsa
    ```
7.  **Set default user and port in ~/.ssh/config, so you can just enter the name next time**
    ```bash
    $ cat ~/.ssh/config
    Host name
    User azadmin
    Hostname 127.0.0.1
    Port 8765
    $ ssh name
    ```
8.  **Generate SSH keys using keygen**
    ```bash
    ssh-keygen -t rsa
    ```
9.  **Copying SSH keys to servers**
    ```bash
    ssh-copy-id <hostname>or<IP address>
    ```
10. **Edit SSH Config File**
    ```bash
    sudo vim /etc/ssh/sshd_config
    ```
11. **Restart SSH service**
    ```bash
    sudo ssh service restart
    or
    sudo sshd service restart
    ```
**[⬆ Back to Top](#ssh)**

### Variables

1.  **Declare a bash variable**
    ```bash
    declare <variable>="<value>"
    ```
2.  **Display value of the variable**
    ```bash
    echo $<variable>
    ```
3.  **Export a bash variable**
    ```bash
    export <variable>
    ```
4.  **Assign integer value to var**
    ```bash
    let "<variable>=<value>"
    ```
5.  **List variables and functions**
    ```bash
    set
    ```
**[⬆ Back to Top](#variables)**  

### File transfer

1.  **Secure file transfer**
    ```bash
    scp <file.txt><server/tmp>
    ```
2.  **Copy a secure file remotely over SSH**
    ```bash
    scp fileName <user>@<remotehost>:<destinationPath>

    Example:
    scp test.txt test@10.0.0.01:/home/azadmin/tmp
    ```
3.  **Sync the contents of a location with the backup directory**
    ```bash
    rsync -a </location> </backup/>
    ```
**[⬆ Back to Top](#file-transfer)**

### Disk usage

1.  ***Disk partition types and sizes**
    ```bash
    fdisk -l 
    ```
2.  **Show free space on system**
    ```bash
    df -h 
    ```
3.  **Show free nodes on system**
    ```bash
    df -l 
    ```
4.  **Show disk usage for all files**
    ```bash
    du -ah 
    ```
5.  **Show disk usage for current directory**
    ```bash
    du -sh 
    ```
6.  **Show target mount point**
    ```bash
    findmnt
    ```
7.  **Validate mount points**
    ```bash
    fstab_mount=($(awk '/^UUID/{print $2}' /etc/fstab))
    current_mount=($(grep -P '^/dev/(?!.*snap)' /proc/mounts |\ 
    awk '{print $2}'))
    for i i ${fstab_mount[@]}
    do
    if [[ ${current_mount[@]} ≠ *"$i"* ]]
    then
    echo "These Mount Point Not Mounnted:"
    grep "$i" /etc/fstab | awk '{print $2}'
    out='fail'
    fi
    done
    if [ =z $out ]
    then
    echo "All Disks Are Mounted Correctly."
    fi
    ```
8.  **Mount a device**
    ```bash
    mount <device> <mountpoint>
    ```

**[⬆ Back to Top](#disk-usage)**

### Process related

1.  **List background processes**
    ```bash
    bg
    ```
2.  **Clear terminal screen**
    ```bash
    clear
    ```
3.  **Bring job to foreground**
    ```bash
    fg <job>
    ```
4.  **Kill the process**
    ```bash
    kill PID               # Shut down process by PID gracefully. Sends TERM signal.
    kill -9 PID            # Force shut down of process by PID. Sends SIGKILL signal.
    pkill foo              # Shut down process by name gracefully. Sends TERM signal.
    pkill -9 foo           # force shut down process by name. Sends SIGKILL signal.
    killall foo            # Kill all process with the specified name gracefully.
    ```
5.  **List files opened by processes**
    ```bash
    lsof
    ```
6.  **Execute command on signal**
    ```bash
    trap "<commands>" <signal>
    ```
7.  **Run a process in background**
    ```bash
    nohup <command> &
    ```
8.  **Report memory map of a process**
    ```bash
    pmap
    ```
9.  **Show active process snapshot**
    ```bash
    ps
    ```
10. **Show processes as a tree**
    ```bash
    pstree
    ```
11. **Show all running processes**
    ```bash
    top                    # List all processes interactively
    htop                   # List all processes interactively
    ps all                 # List all processes
    pidof foo              # Return the PID of all foo processes
    ```
12. **Pause terminal until process completes**
    ```bash
    wait
    ```
13. **Start a process with a given priority**
    ```bash
    nice
    ```
14. **Most recent suspended job to foreground**
    ```bash
    fg
    ```
15. **Give the status of a particular process**
    ```bash
    ps PID
    ```
16. **Change priority of a running process**
    ```bash
    renice
    ```

**[⬆ Back to Top](#process-related)**

### Shell command

1.  **Create command alias**
    ```bash
    alias <alias>="<command>"
    ```
2.  **Schedule a job**
    ```bash
    at <hh:mm>
    ```
3.  **Print command history**
    ```bash
    history
    ```
4.  **Display current jobs and status**
    ```bash
    jobs
    ```
5.  **Display command manual**
    ```bash
    man <command>
    ```
6.  **Remove an alias**
    ```bash
    unalias
    ```
7.  **Set interval to run a command**
    ```bash
    watch -n <interval> <command>
    ```
8.  **Postpone command execution**
    ```bash
    sleep <interval> && <command>
    ```

**[⬆ Back to Top](#shell-command)**

### Searching

1.  **List itmes beginning with x**
    ```bash
    find <./location> -name <x>
    ```
2.  **List items larger than 100MB**
    ```bash
    find <./location> -size <+100M>
    ```
3.  **Search for a pattern in a file**
    ```bash
    find <./location> -name file_pattern

    Example:
    find ./test -name *.txt // ./test/test.txt

    grep <pattern> <file>
    ```
4.  **Search file with name**
    ```bash
    find <./location> -name <filename>
    ```
5.  **Search file with executable action**
    ```bash
    find <./location> -name file_name -exec command

    Example:
    find ./test -name test.txt -exec rm -i {} \;  # Search file and delete it after confirmation
    ```
6.  **Search for empty files or directories**
    ```bash
    find <./location> -empty

    Example:
    find ./test -empty
    //./test/test1
    //./test/test2
    //./test/test1.txt
    ```
7.  **Search for files with permissions**
    ```bash
    find <./location> -perm permission_code

    Example:
    find ./test -perm 664
    ```
8.  **Search text within multiple files**
    ```bash
    find ./ -type f -name file_pattern -exec grep some_text  {} \;

    Example:
    find ./ -type f -name "*.txt" -exec grep 'World'  {} \;  # Hello World
    ```
9.  **Search patterns in files**
    ```bash
    grep pattern files
    grep -i // Case sensitive
    grep -r // Recursive
    grep -v // Inverted search

    Example:
    grep "^hello" test.txt // Hello Andrew
    grep -i "hELLo" text.txt // Hello Andrew
    ```
10. **Find the files by name**
    ```bash
    locate [OPTION] PATTERN # This command is faster compared to find command because it searches database for the filename instead of searching your filesystem.

    Example:
    locate "*.txt" -n 10 // 10 file search results ending with .txt extension
    ```

**[⬆ Back to Top](#table-of-contents)**