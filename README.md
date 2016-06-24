# update-motd.d
Linux motd updater

This is our update-motd.d folder for a better overview of the health of your Linux Server.

You can fork and exdent it.

All our files are GPLv3

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

| Distribution | Version | Checked  |
| :--- | :---: | ---: |
| Debian | 8.5 | ✓ |
| CentOS | 6 | ✓ |
| Ubuntu | 16.04¹ | ✓ |
¹) Needs crudini installed (sudo apt-get install crudini)

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
