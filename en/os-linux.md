---
title: "OS Linux"
description: ""
keywords: ""
lang: "en"
permalink: "os-linux"
aliases:
  - "os-linux"
---

# OS Linux

## Versions

```bash
root@ubuntuserversico:~# cat /proc/version

Linux version 5.15.0-83-generic (buildd@lcy02-amd64-027) (gcc (Ubuntu 
11.4.0-1ubuntu1~22.04) 11.4.0, GNU ld (GNU Binutils for Ubuntu) 2.38) #92-Ubuntu 
SMP Mon Aug 14 09:30:42 UTC 2023
```

## Useful settings

### Open SSH access

Debian

To enable SSH login for a root user on Debian Linux system you need to first configure SSH server. Open /etc/ssh/sshd\_config and change the following line:  
nano /etc/ssh/sshd\_config

FROM:  
PermitRootLogin without-password  
TO:  
PermitRootLogin yes

Once you made the above change restart your SSH server: # /etc/init.d/ssh restart  
\[ ok \] Restarting ssh (via systemctl): ssh.service.

Ubuntu  
http://ubuntuhandbook.org/index.php/2016/04/enable-ssh-ubuntu-16-04-lts/  
sudo passwd root

sudo sed -i 's/prohibit-password/yes/' /etc/ssh/sshd\_config  
or manually open sshd configuration file /etc/ssh/sshd\_config and change line:  
sudo nano /etc/ssh/sshd\_config

FROM:  
PermitRootLogin prohibit-password  
TO:  
PermitRootLogin yes  
Once you have made the above configuration change restart ssh daemon:  
$ sudo systemctl restart sshd  
(or restart server)

### Change language

```bash

env | grep LANG
export LANG=en_US.UTF-8
dpkg-reconfigure locales
```

### Change timezone

```bash

timedatectl 
set-timezone America/New_York
```

### Change server name

The procedure to change the computer name on Ubuntu Linux:

Type the following command to edit /etc/hostname using nano or vi text editor:

```bash
sudo nano /etc/hostname
```

Delete the old name and setup new name. Next Edit the /etc/hosts file:

```bash
sudo nano /etc/hosts
```

Replace any occurrence of the existing computer name with your new one.  
Reboot the system to changes take effect:

```bash
sudo reboot
```

## Users and groups

entering root mode

```bash

sudo su
```

setting a password (and actually activating) root

```bash

sudo passwd root
```

[https://andreyex.ru/linux/ponimanie-fajla-etc-shadow/](https://andreyex.ru/linux/ponimanie-fajla-etc-shadow/) How to check (password is encrypted). If the password field contains an asterisk ( \*) or exclamation mark ( !), the user will not be able to log in using password authentication. Other login methods, such as key-based authentication or switching to user, are still allowed

```bash

sudo cat /etc/shadow | grep root
```

Utilities:

* sudo is a utility for launching programs with superuser rights, for example, to run the mc program with superuser rights, you need to type "sudo mc" - this will allow you to edit system files in the etc folder.
* whoami - display the name under which you are registered.

For a complete list of user accounts, one account per line:

```bash
less /etc/passwd
```

The /etc/passwd file consists of user records, one to a line. Each record contains multiple fields, separated by colons (:). The fields are:

• username • encrypted password (or x if shadow passwords are in use) • UID • default GID • real name (also known as the GECOS field) • home directory • default shell  
For a complete list of groups, one group per line:

```bash
less /etc/group
```

The /etc/group file consists of group records, one to a line. Each record contains multiple fields, separated by colons (:). The fields are:

• group name • encrypted group password (or x if shadow passwords are in use) • GID • group members' usernames, comma-separated

Adding a user

```bash
adduser newuser
```

temporary (until the exit command) switching to a new user

```bash
su - newuser
```

Changing the root password  
•To change password of any account when login as root, use command: passwd  
•To change password of a group, use command: passwd -g

```bash
sudo passwd root
```

Or, if you're running as root already (which you shouldn't be), just:

```bash
passwd
```

Deleting a user. User accounts can be removed using the userdel command. The basic syntax of the userdel command is userdel username.

Permissions

chmod \<permissions=""\> \<file\> - change the permissions for a file that you own. (-R recursion)  
reading - read (r), writing - write (w), execution - execute (x) and three types of users:  
the owner of the file is owner (u), members of the same group as the owner of the file (g) and everyone else (o).  
You can check your current access rights in the following way:

```bash
ls -l filename
```

If the file is accessible by all means to all users, then the following combination of letters will appear next to the file name: rwxrwxrwx The first three letters are the access rights for the file owner. The second triplet is the access rights for his group. The next three are the access rights for others. Lack of access rights is shown as "-"

For example:

This command will allow you to set read permissions for the junk file for everyone (all=user+group+others):

```bash
chmod a+r junk
```

This command will remove the executable file permission from everyone except the user and group:

```bash
chmod o-x junk
```

chown \<new\_owner\> \<files\> - change file owner  
chgrp \<new\_group\> \<files\> - change the ownership group for files

## Working with the file system

### File Manager

```bash
apt-get install mc
```

### Information

du

Without passing any parameters, the du command prints the name and size of each folder in the current path, including all subdirectories in the output: To get folder sizes in a more readable format, namely kilobytes (K), megabytes (M) or gigabytes (G) use the switch -h:du -h

du -h /home

To find out the total size of a specific folder, call the du command with the -s switch:  
du -hs /home

Another handy du command option is the --max-depth switch, which specifies the depth of folders to be viewed. If you set the depth to one, you can see the total sizes of all folders in the specified path. Execute:du -h --max-depth=1

For example

```bash

du -h /var/lib/docker/containers --max-depth=1
```

Free space in directory  
df /mnt/sdb1

### Moving through files, searching

pwd -- show current location

ls - List the files in the current directory. (ls -l - with rights) ls -a command in Linux/Unix | show all/hidden files

cd \[directory\] - change the current directory. If a directory name is not specified, the user's home directory becomes the current directory.

cat \<filename\> - outputs the contents of the file to standard output (default - to the screen).

find \<directory\> -name filename - find a file named "filename" and display the search result on the screen. The search starts from the directory \<directory\>; "filename" may contain a search mask. (searches only in the current level)

### Copying, deleting

**cp** \<copy\_what\> \<copy\_where\> - copy files.

copy the directory

```bash
cp -r /mnt/tdisks/U/Distr /mnt/pdisks/U/
```

mv \<what to move\> \<where to move\> - move or rename the file.

ln -s \<link\_to\> \<link\_name\> - create a symbolic link.

rm \<files\> - delete files.

mkdir \<directory\> - create a new directory.

mkdir -p \<directory\>\</directory\>directory/directory\> - create a new directory.

rmdir \<directory\> - delete an empty directory.

rm -rf \<files and/or="" directories=""\> (recursive delete) - delete files or directories and their subdirectories.

For example, deleting all files in a directory

rm -rf /mnt/pdisks/U/\*

Note:

cp behavior is unexpectedly different if dir2 already exists and will not be created by the cp command.

cp -r dir1 dir2

# and similarly

cp -r dir1/ dir2

For an existing directory, dir2 will create a copy of the directory dir1 into dir2/dir1 instead of copying the contents of dir1 into dir2.

Whereas

cp -r dir1/. dir2

It will copy the contents of dir1 to dir2.

This is a non-obvious feature of the cp implementation. For example, rsync does not do such strange things and the following entries are equivalent:

rsync -a dir1 dir2/  
rsync -a dir1/. dir2/

(but rsync will have different behavior for writing dir2/ and dir2 for an existing directory; it is better to specify it as autocomplete suggests, ending with the path /)

### rsync

rsync - copying (synchronization) with progress indicator

rsync is a utility for efficiently transferring and synchronizing files across computer systems. rsync has one with --progress parameter. The -a will keep permissions,etc, and -h will be human readable.

rsync -ah --progress source destination

rsync -rvz --progress input/images output/

Use "n" to fake copy

rsync -rvzn --progress input/images output/

### scp

```bash
scp -P 2023 file.tar.gz root@servername:/mnt/tdisks/U/
```

### Editing files

#### nano

apt-get install nano

nano /path/file

[http://help.ubuntu.ru/wiki/nano](http://help.ubuntu.ru/wiki/nano)

Ctrl+X or F2 - Close and exit

Ctrl+O or F3 - Save current file

#### vi

If you want to edit a file using terminal, press i to go into insert mode. Edit your file and press ESC and then :w to save changes and :q to quit. However, you can combine these two like :wq to write and quit the vim editor.

To exit the vi editor without saving the changes made to the file, use the command **:q!** . When the : command is entered, the cursor moves to the last line of the screen, and thus the editor is in last line mode. In this mode it is possible to enter some advanced commands. One of them is the q! command, which ends work with the vi editor without saving the changes made. The **:wq** command first saves the file with the changes made and then exits the vi editor. The **ZZ** command (issued in command mode, i.e. without entering the : command) is equivalent to the **:wq** command. If the file has not changed since the last modification, then the creation time of the file will also not be changed. Recall that in last line mode, command entry is completed by pressing the Enter key.  
To save the file but not exit the vi editor, use the **:w** command.

### Compressing

compressed files can be recovered using either "gzip -d" or the gunzip command.

gunzip \[file\] - decompresses files compressed using the gzip utility.

The Gunzip command deletes the archive file after extracting it. However, if you want the archive to remain, you can do so using the -c option on the command line.

```bash
gunzip -c file1.gz > file1
gunzip -c file.gz > /THERE/file
```

unzip \[options\] \[zipped file\] - using this command you can unzip a file compressed with the zip archiver.

Unpacking tar.gz archive:

```bash
tar xzf archive-name.tar.gz
```

tar --xf tar unzipping (the archive on Windows is prepared using 7Z or on Windows 10 using the built-in OS command tar Then check file names with nonASCII)

```bash
# tar -xf file_name.tar -C /target/directory
# tar -xf file_name.tar.gz --directory /target/directory
```

[https://www.tecmint.com/extract-tar-files-to-specific-or-different-directory-in-linux/](https://www.tecmint.com/extract-tar-files-to-specific-or-different-directory-in-linux/)

Creating a tar.gz archive: tar -cvzf folder1.tar.gz /var/www

```bash
tar -cvzf folder.mnt.tar.gz /mnt
```

### Downloading files from outside

curl http://proft.me - get the contents of the main page  
curl -o index.html http://proft.me - get the contents of the main page into the file index.html

Curl on Ubuntu documentation [https://manpages.ubuntu.com/manpages/focal/man1/curl.1.html](https://manpages.ubuntu.com/manpages/focal/man1/curl.1.html)

## Commands and scripts

### Run

Set rights:

```bash
chmod +x filename.sh
```

./Program\_Name - run the executable file in the current directory if the current directory is not in the list of directories specified in the PATH environment variable.

alias ls="ls -Fskb --color" - create an alias so that you can run a more complex combination of commands with one command. Place the alias creation in the /etc/bashrc file if you want these aliases to be available to all users on your system

All log files should be in one directory, which is located here: /var/log/

### Scripts

[https://wiki.debian.org/BashScripting](https://wiki.debian.org/BashScripting)  
Some bash shell scripting rules:

1) The first line in your script must be {#line-33}

\#!/bin/bash {#line-35}

... that is a # (Hash) followed by a ! (ban) followed by the path of the shell. This line lets the environment know the file is a shell script and the location of the shell. {#line-37}

2) Before executing your script, you should make the script executable. You do it by using the following command: {#line-39}

$ chmod ugo+x your\_shell\_script.sh {#line-41}

3) The name of your shell script must end with a .sh . This lets the user know that the file is a shell script. This is not compulsary but is the norm.

Run function from script (Example run function zero\_downtime\_deploy) [https://stackoverflow.com/questions/8818119/how-can-i-run-a-function-from-a-script-in-command-line](https://stackoverflow.com/questions/8818119/how-can-i-run-a-function-from-a-script-in-command-line)

```bash
. ./redeploy-app.sh && zero_downtime_deploy
```

[https://www.redhat.com/sysadmin/arguments-options-bash-scripts](https://www.redhat.com/sysadmin/arguments-options-bash-scripts) Adding arguments and options to your Bash scripts

### Environment Variables

set|more - display the current values of environment variables. (Not for all shells. For csh/tcsh - printenv | more, although set will also show useful information.)

echo $PATH - print the value of the environment variable "PATH" The echo command can be used to print the values of any environment variables. Use the set or printenv commands to get a complete list.

### View services and processes

! Depending on how you look at it, ps doesn't tell you how much memory a process actually uses. What this utility does do is show how much memory each process will take up as if it were the only process running.

ps aux  
ps ax -o pid,cmd,size  
ps ax | grep 'search for process by part of name'  
ps aux | grep 'jdk'

ps | grep \<your\_username\> -display all processes running on the system under your username.

ps -eo pmem,pcpu,rss,vsize,args | sort -k 1 -r | less To see a list of your running processes sorted by memory use: (! check sorting by two digits 22% comes after 3% because of two digits)

The ps command can conveniently use the pipeline and the less utility to scroll through the displayed information using the up buttons and down, for example ps ax | lessThe second option is to use the top command. it displays information about the system load and updates it in real time.

pstree displays a tree of processes (useful for counting identical processes)

An alternative to ps is the top command, which conveniently displays constantly updated information on the screen, but top is limited by the size of the window, so anything that cannot fit on the screen is simply ignored.

# top -p 897110

kill - "kill" the process. First, determine the PID of your "killed" process using ps.  
killall \<program\_name\> - "kill" all processes by program name.

### Turn on, turn off, reboot

The shutdown command is the main command to control stopping or rebooting a Linux system.

```bash
shutdown -r now
```

```bash
shutdown -h now
```

When using the shutdown command, you can specify a reboot at a specific time with the display of informative messages.  
shutdown -r 10:30 "REBOOT SYSTEM"

The reboot command performs all the necessary operations to stop the system; this command can be called with the shutdown -r command, but can be used separately. This command logs the time the system was stopped, kills unfinished processes, executes the sync system call, waits for disk writing to complete, and only then stops the kernel and reboots the Linux system.

```bash
reboot
```

The halt command.  
The command is identical to the reboot command in its actions, the difference is that the halt command shuts down the system.

```bash
halt
```

Use the poweroff command.  
The poweroff command is identical to the halt command, except that after stopping the system, a special request is sent to the power management system to turn off power, allowing systems to be shut down remotely.

```bash
poweroff
```

#### Disable sleeping mode

[How do I disable my system from going to sleep?](https://askubuntu.com/questions/47311/how-do-i-disable-my-system-from-going-to-sleep)

On Ubuntu 16.04 LTS, I successfully used the following to disable suspend:

```bash
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```

And this to re-enable it: `sudo systemctl unmask sleep.target suspend.target hibernate.target hybrid-sleep.target`

### Long processes through "screen"

sudo apt-get install screen

1. log into the remote machine (via ssh)
2. run screen there
3. run some long process inside the screen session
4. detach the screen session by pressing CTRL-A and then d (in general, all internal screen commands start with CTRL-A, for example CTRL-A + ? will show quick help)
5. exit the remote system (everything running inside screen will continue to work)
6. go to dinner, go to bed, go on vacation, do other things
7. When you want, log back into the remote machine and connect to an already running screen session by typing screen -r.

Additional commands:

list of running processes

screen -ls

Closing from inside

exit

Closing from outside session you can copy fromscreen -ls)

screen -X -S \[session # you want to kill\] quit

Ctrl+a -\> c With this command we created a new screen and now they work simultaneously

To switch between screens, you can either specify the screen number or select a screen from the list:  
Ctrl+a -\> 0 will take us to screen 0.  
Ctrl+a -\> " will bring up a menu for selecting a screenshot  
Ctrl+a -\>n will switch to the next screen  
Ctrl+a -\>p will switch to the previous screen

Regions are being closed with hotkeys  
Ctrl+a -\>Q Close all regions except the current one  
Ctrl+a -\>X Close current region

### Scheduler - crontab

[https://www.computerhope.com/unix/ucrontab.htm](https://www.computerhope.com/unix/ucrontab.htm)

List of tasks for the current user:

```bash
crontab -l
```

List of tasks for user with name vasua:

```bash
crontab -u vasua -l
```

List of tasks for all users

```bash
for user in $(cut -d':' -f1 /etc/passwd); do crontab -u $user -l; done
```

Edit

```bash
crontab -e
```

On a default installation the cron jobs get logged to /var/log/syslog

## Disk and partition layout, formatting, mounting, disk loading information

### Displaying information (including information about free space)

df -h - display information about free and used space on disks (mounted partitions)

hdparm -I /dev/sda will output information about the physical media mounted on /dev/sda

Working with the fdisk utility on Linux [http://www.oldnix.org/fdisk-linux/](http://www.oldnix.org/fdisk-linux/)

fdisk -l print full information

### Adding a Hard Drive in Linux

[http://www.linuxlib.ru/iron/hddadd.htm](http://www.linuxlib.ru/iron/hddadd.htm) [http://mydebianblog.blogspot.ru/2008/09/linux.html](http://mydebianblog.blogspot.ru/2008/09/linux.html)

[https://pve.proxmox.com/wiki/Resize\_disks](https://pve.proxmox.com/wiki/Resize_disks)

view information about all physical and virtual disks

```bash
fdisk -l
```

view information about the first physical or virtual disk

```bash
fdisk -l /dev/sda
```

find your new drive. it can be for example /dev/vdb /dev/vdc /dev/sda4 - this must be taken into account in further commands

```bash
fdisk /dev/vdc
```

Create a new partition with n. Then select the partition type by entering the p command. Leave the remaining parameters unchanged by simply pressing Enter. To save your changes, enter the w command.

formats the vdc1 partition into ext4 format

```bash
mkfs.ext4 /dev/vdc1
```

create the mount folder

```bash
mkdir /mnt/disk2
```

```bash
mount -o barrier=0 /dev/vdc1 /mnt/disk2
```

```bash
echo "/dev/vdc1 /mnt/disk2 ext4 barrier=0 0 1" >> /etc/fstab
```

Check the disk names in the system, for example, with the lsblk command

### Mounting

Simple

```bash
mount -t ext3 /dev/sda4 /mnt/sda4
```

mounting with opening rights  
(may give a parameter mismatch error, which depends, in particular, on the type of file system)

```bash
mount -t ext4 -o umask=000 UUID=4b1cfd17-5f09-42ba-8cbe-d0c959562489 /mnt/drive
```

```bash

mount -t auto /dev/sdb1 /mnt/sdb1 -o umask=0,nls=utf8
```

### Permanent mount

Note: If there is an error in the commands, the system will not start

For permanent mounting add it to /etc/fstab

```bash
/dev/sda4 /mnt/sda4 ext3 defaults 0 0
```

With expanded access rights (umask=0 may give an error)

```bash
/dev/sdb1 /mnt/sdb1 auto umask=0,nls=utf8,exec,user,auto,rw 0 0
```

View mounted

```bash
cat /etc/fstab view automount
```

## Monitoring

### Memory

free - display information on memory usage. (outputs in kb by default)  
\-b,-k,-m,-g show output in bytes, KB, MB, or GB

### Hardware Monitoring

lm-sensors - a set of utilities for reading the values of temperature, voltage and cooler speed sensors. Using these utilities, you can answer the question "What is the current temperature of my processor?"

1\.Install lm-sensors:

apt-get install lm-sensors

2. Determine the presence of sensors in the system:

sensors-detect

3. Load the missing drivers:

modprobe \<missing modules=""\>

4. And that's it, look at the sensor values:

sensors  
\</missing\>

## References

[http://www.jinr.ru/unixinfo/usersguide/](http://www.jinr.ru/unixinfo/usersguide/) (lang: rus)

Red Hat Enterprise Linux 4 Руководство по системному администрированию  
[http://www.rhd.ru/docs/manuals/enterprise/RHEL-4-Manual/sysadmin-guide/index.html](http://www.rhd.ru/docs/manuals/enterprise/RHEL-4-Manual/sysadmin-guide/index.html) (lang: rus)

[http://homes-smart.ru/index.php/oborudovanie/raspberry-pi/azbuka-po-linux-sistemam](http://homes-smart.ru/index.php/oborudovanie/raspberry-pi/azbuka-po-linux-sistemam) (lang: rus)
