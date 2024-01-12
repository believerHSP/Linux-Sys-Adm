# Linux-Sys-Adm
Increasing Productivity as an Engineer while interacting with server side OS.

# 1. Error while apt update inside container:
https://stackoverflow.com/questions/56579468/list-directory-var-lib-apt-lists-partial-is-missing-acquire-20-not-a-direc

lenovo@ipa:~/filestash$ docker exec -it ccd99805c069 bash 
filestash@ccd99805c069:/app$ 
filestash@ccd99805c069:/app$ sudo apt update 
bash: sudo: command not found
filestash@ccd99805c069:/app$ apt update 
Reading package lists... Done
E: List directory /var/lib/apt/lists/partial is missing. - Acquire (13: Permission denied)
filestash@ccd99805c069:/app$ apt-get update 
Reading package lists... Done
E: List directory /var/lib/apt/lists/partial is missing. - Acquire (13: Permission denied)
filestash@ccd99805c069:/app$ 
filestash@ccd99805c069:/app$ apt install apache2-utils
E: Could not open lock file /var/lib/dpkg/lock-frontend - open (13: Permission denied)
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), are you root?
filestash@ccd99805c069:/app$ cat /etc/os-release  
PRETTY_NAME="Debian GNU/Linux 12 (bookworm)"
NAME="Debian GNU/Linux"
VERSION_ID="12"
VERSION="12 (bookworm)"
VERSION_CODENAME=bookworm
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
filestash@ccd99805c069:/app$ sudo apt update 
bash: sudo: command not found
filestash@ccd99805c069:/app$ apt update 
Reading package lists... Done
E: List directory /var/lib/apt/lists/partial is missing. - Acquire (13: Permission denied)
filestash@ccd99805c069:/app$ 

lenovo@ipa:~/filestash$ docker ps 
CONTAINER ID   IMAGE                       COMMAND                  CREATED      STATUS        PORTS                                       NAMES
5fa99f9b9d47   onlyoffice/documentserver   "/app/ds/run-documen…"   3 days ago   Up 28 hours   80/tcp, 443/tcp                             filestash_oods
ccd99805c069   machines/filestash          "/app/filestash"         3 days ago   Up 28 hours   0.0.0.0:8334->8334/tcp, :::8334->8334/tcp   filestash

lenovo@ipa:~/filestash$ sudo docker exec -u 0 -it ccd99805c069 bin/bash
[sudo] password for lenovo: 
OCI runtime exec failed: exec failed: unable to start container process: exec: "bin/bash": stat bin/bash: no such file or directory: unknown

lenovo@ipa:~/filestash$ sudo docker exec -u 0 -it ccd99805c069 bash
root@ccd99805c069:/app# 
root@ccd99805c069:/app# 
root@ccd99805c069:/app# apt update 
Get:1 http://deb.debian.org/debian stable InRelease [151 kB]
Get:2 http://deb.debian.org/debian stable-updates InRelease [52.1 kB]
Get:3 http://deb.debian.org/debian-security stable-security InRelease [48.0 kB]
Get:4 http://deb.debian.org/debian stable/main amd64 Packages [8787 kB]
Get:5 http://deb.debian.org/debian stable-updates/main amd64 Packages [12.7 kB]                                                                        
Get:6 http://deb.debian.org/debian-security stable-security/main amd64 Packages [134 kB]                                                               
Fetched 9185 kB in 11s (863 kB/s)                                                                                                                      
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
11 packages can be upgraded. Run 'apt list --upgradable' to see them.
root@ccd99805c069:/app# 


# SQL :

With as 
generate series 
Joins : left join, cross join.
