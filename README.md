# update-motd.d

Hello this is our /etc/update-motd.d folder. You can download it in your distribution with the git command
```shell
git clone https://github.com/SHelfinger/update-motd.d/ ~/
```
This command will add the complete git repo inside your home folder (`cd ~/`)

Usually you have already the chmod +x on all files, but when this isn't please make them executionable (`chmod +x *-*`) inside the folder.

As you are done with testing each .sh file (`./10-version` etc) feel free to install it
```shell
cp 10-version /etc/update-motd.d/10-version
cp 20-cpu /etc/update-motd.d/20-cpu
cp 21-temp /etc/update-motd.d/21-temp
cp 30-hdd /etc/update-motd.d/30-hdd
cp 40-memory /etc/update-motd.d/40-memory
cp 50-lastlogin /etc/update-motd.d/50-lastlogin
cp 90-fail2ban /etc/update-motd.d/90-fail2ban
```
(Remember on some .sh files you need special programs, usually bc and crudini)

Now we need to tell your SSH Daemon that he needs to get the `/run/motd` file.

Make first sure that SSHD is restarted (`service sshd restart`) then check is motd updated (`cat /run/motd`)

When you see your motd, perfectly now we insert this in your pam.d settings.

Switching the folder
`cd /etc/pam.d/`

Open the file sshd
`sudo nano /etc/pam.d/sshd`

Change 
`session    optional     pam_motd.so  motd=/run/motd.dynamic`
TO
`session    optional     pam_motd.so  motd=/run/motd`

CTRL+O AND CTRL +X

Now reloggin in your Server

## Content

##### Table of contents
[All together](https://github.com/SHelfinger/update-motd.d#all-together)

[10-version](https://github.com/SHelfinger/update-motd.d#10-version)

[20-cpu](https://github.com/SHelfinger/update-motd.d#20-cpu)

[21-temp](https://github.com/SHelfinger/update-motd.d#21-temp)

[30-hdd](https://github.com/SHelfinger/update-motd.d#30-hdd)

[40-memory](https://github.com/SHelfinger/update-motd.d#40-memory)

[50-systop](https://github.com/SHelfinger/update-motd.d#50-systop)

[50-lastlogin](https://github.com/SHelfinger/update-motd.d#60-lastlogin)

[90-fail2ban](https://github.com/SHelfinger/update-motd.d#90-fail2ban)


---
### All together
We have created some more features where aren't in this git. When you really need it, send us a mail/message.
![100-all](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/100-all.png "100-all")

---
### 10-version
This .sh will output the Distribution, Version Number (Code name, Kernel, Architecture)

Debian output:
```shell
Linux Debian 8.5 (jessie 4.4.8-1-pve x86_64)
```

Screenshot:
![10-version](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/10-version.png "10-version")

---
### 20-cpu
This .sh will output all and each core % load. The histogram is User, Nice, System, I/O Wait and Free)

Debian output:
```shell
CPU ALL (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 4%/96%
     01 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 8%/92%
     02 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 8%/92%
     03 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 7%/93%
     04 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 7%/93%
     05 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 8%/92%
     06 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 5%/95%
     07 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 5%/95%
     08 (Load/Idle) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 5%/95%
```

Screenshot:
![20-cpu](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/20-cpu.png "20-cpu")

---
### 21-temp
This .sh will output all the core's temperture. (Remember i7 has not 8 cores! 4 cores, 4 siblings see cat /proc/cpuinfo)

Debian output: 
```shell
Core1: 41° Core2: 42° Core3: 40° Core4: 35°
```

Screenshot:
![21-temp](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/21-temp.png "21-temp")

---
### 30-hdd
This .sh will output all hard disc's with usage/free diagram.

Debian output:
```shell
HDD /dev/md1 (Usage/Free) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 11%/89%
HDD /dev/md2 (Usage/Free) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 5%/95%
HDD /dev/md3 (Usage/Free) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 4%/96%
```

Screenshot:
![30-cpu](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/30-hdd.png "30-hdd")

---
### 40-memory
This .sh will output the usage of the memory (User, Buffers, System and Cache)

Debian output:
```shell
Memory (Mem) (UBSC/Free) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 22%/78%
Memory (Swap) (Usage/Free) [IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII] 2%/98%
```

Screenshot:
![40-memory](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/40-memory.png "40-memory")

---
### 50-systop
This .sh will output your system network information (Hostname, DNS, FQDN and IP)

Debian output:
```shell
Hostname proxmox DNS shelfinger.eu FQDN proxmox.shelfinger.eu IP 144.76.32.43
```

Screenshot:
![50-systop](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/50-systop.png "50-systop")

---
### 60-lastlogin
This .sh will output the last login access and currently IP

Debian output:
```shell
Current IP: 41.207.182.235 Last IP: 41.207.182.235 Last Access: Thu Jun 23 20:35 - 00:03
```

Screenshot:
![60-lastlogin](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/60-lastlogin.png "60-lastlogin")

---
### 90-fail2ban
This .sh will output the Top 10 from todays bans.

Debian output:
```shell
Fail2Ban Today's Ban Statistics
        1       155.133.38.33   (recidive)
        1       155.133.38.33   (sasl)
```

Screenshot:
![90-fail2ban](https://raw.githubusercontent.com/SHelfinger/update-motd.d/master/images/90-fail2ban.png "90-fail2ban")
