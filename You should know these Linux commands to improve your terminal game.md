-----
**You should know these Linux commands to improve your terminal game 😎🖥️**

Linux is an operating system (OS) for computers, servers, mainframes, mobile devices, and embedded devices that is Unix-like, open source, and community-developed. It is one of the most widely supported operating systems, with support for almost every major computer platform, including x86, ARM, and SPARC.

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.001.jpeg)

Until recently, Linux was primarily used for servers and was not considered suitable for desktop computers. However, its user interface and ease of use have steadily improved in recent years. Linux is now user-friendly enough to replace Windows on desktop computers. It is used by hundreds of thousands of people all over the world.

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.002.jpeg)

Today we’ll look at some lesser-known linux commands that will get your terminal game going. If not that, it would undoubtedly improve your terminal game. 💯

**Screen 💻**

Screen is a full-screen window manager that creates a single window with a running shell and allows multiple screen windows to run within the same session. It’s most useful when you’re running a long remote task and are concerned about your SSH session terminating and ruining everything. Screen will continue to run your commands even if you disconnect and the window is not visible to you.

\# Starting a screen session
screen 

\# Listing running screen sessions
screen -ls

\# Attaching to screen session
screen -r 

**Wall 🧱**

Wall is a command-line utility that displays a message on all logged-in users’ terminals. Messages can be typed into a terminal or the contents of a file. To send a message to a specific user, use the write command instead of the wall command.

\# This option will suppress the banner.
wall -n

\# To broadcase certain message
wall "Cleanup window currently running!"

*Broadcast message from devang@localhost:* Cleanup window currently running!

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.003.jpeg)

**Ncdu 💾**

The ncdu command provides a quick, convenient view for disk usage. The ncdu command displays disc usage in a useful and convenient manner. The name is an abbreviation for “NCurses disc usage.” This means that it is based on ncurses, which is a terminal control library used on Unix/Linux systems like curses. You can use it to see what directories are using the most disk space quickly and easily.

\# For opening ncdu help
ncdu --help

ncdu  

`  `-h,--help                  This help message
`  `-q                         Quiet mode, refresh interval 2 seconds
`  `-v,-V,--version            Print version
`  `-x                         Same filesystem
`  `-e                         Enable extended information
`  `-r                         Read only
`  `-o FILE                    Export scanned directory to FILE
`  `-f FILE                    Import scanned directory from FILE
`  `-0,-1,-2                   UI to use when scanning (0=none,2=full ncurses)
`  `--si                       Use base 10 (SI) prefixes instead of base 2
`  `--exclude PATTERN          Exclude files that match PATTERN
`  `-X, --exclude-from FILE    Exclude files that match any pattern in FILE
`  `-L, --follow-symlinks      Follow symbolic links (excluding directories)
`  `--exclude-caches           Exclude directories containing CACHEDIR.TAG
`  `--confirm-quit             Confirm quitting ncdu
`  `--color SCHEME             Set color scheme

**Netcat 🐈**

Netcat, or nc, is primarily used for port scanning, but it is also an excellent utility networking tool for system administrators to have on hand for any task. Netcat can scan for ports, copy files, forward ports, connect to proxy servers, and host websites… It’s safe to say that it’s extremely adaptable.

\# Scan a single port
nc -v -w 3 z 192.168.16.1 22     

\# Scan multiple ports
$ nc -v -w 2 z 192.168.56.1 22 80  

\# Scan range of ports
$ nc -v -w 2 z 192.168.56.1 20-25

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.004.png)

**Shred 📆**

When was the last time you deleted a file from your Linux system? How did you manage it? Did you use rm and then abandon it? If there was any sensitive data in that file, you might want to reconsider using rm for that purpose. This is where shred enters the picture. When you delete a file permanently or from the trash, the pointer pointing to it loses its address, and the data of the file is sent to a sector in hard disc and is considered unallocated space, which can be easily recovered.

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.005.png)

This small utility will securely erase a file by writing random data over top of it multiple times.

\# For shredding a particular file
shred -u <filename>

**Split 🖖**

Simple, effective, and even more adaptable than a command with a similar name in your high-level programming language. Split a file based on any number of criteria, from the number of lines to the length in bytes. Split provides more flexibility than simply splitting strings or line breaks.

Large files are split into smaller files using Linux. It divides files into 1000 lines (by default) and allows users to change the number of lines as needed.

\# Spliting file based on n.o of lines
split -l 6 random.txt split\_file

\# Spliting file based on n.o of bytes
split -b 16 index.txt index

**tc 🚦**

Tc is used in the Linux kernel to configure Traffic Control. The following are the components of traffic control: Shaping. The rate of transmission of traffic is controlled when it is shaped. Shaping is used for more than just reducing available bandwidth; it is also used to smooth out traffic bursts for better network behaviour.

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.006.jpeg)

Traffic control (tc) is an extremely useful Linux utility that allows you to configure the kernel packet scheduler. If you’re looking for reasons to fiddle with the kernel scheduler, here are a few: First, it’s fun to experiment with the various options and become acquainted with all of Linux’s features. Furthermore, you can use Linux’s useful tools to simulate packet delay and loss for UDP or TCP applications, or limit the bandwidth usage of a specific service to simulate Internet connections (DSL, Cable, T1, etc).

\# Set a delay of 100ms and random +-10ms uniform distribution
tc qdisc change dev eth0 root netem delay 100ms 10ms

\# limit the egress bandwidth we can use the following command
tc qdisc add dev eth0 root tbf rate 1mbit burst 32kbit latency 400ms

**Tcpdump 🗑️**

Used to record and analyse traffic to and from your system. It is a powerful and versatile tool that specialises in network debugging and troubleshooting but can also be used as a security tool.

\# To capture specific number of packets
sudo tcpdump -c 4 -i eth0

\# To display all available interfaces
sudo tcpdump -D

\# To capture packets with ip address
sudo tcpdump -n -i wlo1

**Xargs 🤌**

The xargs command constructs and executes commands entered via standard input. It converts the input into a command argument for another command. 

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.007.jpeg)

This feature is especially useful in file management, where xargs is used in conjunction with rm, cp, mkdir, and other commands of a similar nature.

\# To generate a compact list of all Linux user accounts
cut -d: -f1 < /etc/passwd | sort | xargs

\# To find file(s) in a directory and delete them as well
find /Users/yourusername -name "random" -type d -print0 | xargs -0 -t /bin/rm -rf "{}"

**lsof 📂**

As we all know, Linux/Unix treats everything as if it were a file (pipes, sockets, directories, devices, etc). When a disc cannot be unmounted because the files are in use, one of the reasons to use the lsof command. We can easily identify the files that are in use with the help of this command.

lsof is a single command that serves a single purpose: listing open files. This is especially useful when dealing with mounting issues that indicate that files are being used. This command quickly determines which files are currently being used by which processes.

\# Yup that's it.. 😇
lsof

**htop ⚙️**

In a Linux system, the htop command is a command-line utility that allows the user to interactively monitor the system’s vital resources or the server’s processes in real time. htop is a newer programme than top command, and it offers many advantages over top command. 

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.008.jpeg)

htop supports mouse operation, outputs in colour, and provides visual indications of processor, memory, and swap usage. htop also prints full command lines for processes and allows for vertical and horizontal scrolling for processes and command lines.

\# **-d –delay :** Used to show the delay between updates, in tenths of seconds.
\# **-C –no-color –no-colour** : Start htop in monochrome mode.
\# **-h –help :** Used to display the help message and exit.
\# **-u –user=USERNAME :** Used to show only the processes of a given user.

htop -u yourUsername

-----
That concludes some of the useful options of common Linux commands you should have been aware of earlier. I’m always amazed by Linux commands when I come across these hidden gems.

![](Aspose.Words.a30dbeda-95af-4a58-8a28-92ac095a6b0c.009.jpeg)

If you believe you are aware of a command option that is not widely used but is extremely useful, please share it with us in the comments.

I have also compiled this as a readme over my GitHub. Fancy checking it out? here it is.

**Github URL for this article 💻**

**Let’s connect and chat! Open to anything under the sun 🏖️🍹**

**🐦 Twitter :** [devangtomar7](https://twitter.com/devangtomar7)
**🔗 LinkedIn : [devangtomar](https://www.linkedin.com/in/devangtomar)**
**📚 Stackoverflow :** [devangtomar](https://stackoverflow.com/users/8198097/devangtomar)
**🖼️ Instagram :** [be_ayushmann](https://instagram.com/be_ayushmann)
Ⓜ️ **Medium :** [Devang Tomar](https://medium.com/u/8f5e1c86129d?source=post_page-----e42119a306ca--------------------------------)
☊ **Hashnode :** [devangtomar](https://devangtomar.hashnode.dev/)
**🧑‍💻 Dev.to :** [devangtomar](https://dev.to/devangtomar)




