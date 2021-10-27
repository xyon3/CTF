# [THM] Pickle Rick writeup

ps: I didn't got to screenshot the actual procedure because i'm dum. But i made notes! check [files](files/notes.md)

## Scanning and Enumeration

I scanned the IP ADDRESS using Nmap, Gobuster, and Nitko

```
NMAP SCAN

===Initial===

Starting Nmap 7.80 ( https://nmap.org ) at 2021-10-27 20:40 PST
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.6 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 f4:ae:ca:49:0a:98:39:e9:1e:af:c0:6f:ba:14:79:15 (RSA)
|   256 2a:46:cf:cc:83:70:09:6f:87:15:73:e0:c0:28:b4:08 (ECDSA)
|_  256 99:77:db:8a:1c:e9:82:42:30:3c:b9:1a:a6:32:f4:42 (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Rick is sup4r cool
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Nmap done: 1 IP address (1 host up) scanned in 25.16 seconds
           Raw packets sent: 1121 (49.300KB) | Rcvd: 1002 (40.088KB)

```


```
GOBUSTER SCAN

    common.txt
        /.hta (Status: 403)
        /.htaccess (Status: 403)
        /.htpasswd (Status: 403)
        /assets (Status: 301)
        /index.html (Status: 200)
        /robots.txt (Status: 200)       <--- Wubbalubbadubdub
        /server-status (Status: 403)


```


nikto did not find anything so i decided to take a little look on some write up.

and saw that the other write up's nikto saw a login.php dir in IP:80 and mine's scanning the system for like 30 mins!! :angy face:
```
FROM ANOTHER WRITE-UP
    /login.php found from nikto (but my nikto scan failed to see it)
```


So then I used the commented username from the source code and the text from the robots.txt as the password and gen into portal.php

all of the clickable stuff in the header are useless so i focused on the bar thinggy

I tried 'ls' and got #picture_wwwdir#

tried 'cat' #failed_picture#

pwd #picture#
whoami #picture#

python3 --version #picture#
so then i made a simple http server using
```bash
    python3 -m http.server 8000
```
then when I go to [IP]:8000/ i get the index.html getting served. I tried adding /clue.txt and presented with this
#picture_DOWNLOAD#
so i downloaded all .php files for inspection

in the portal.php file I saw all the commands that is being sanitized.

and this is where i realized i'm stupid. I could just use 'less' command instead of serving the directory with python. on top of that the python command i used crashed the box and needed to restart it.

i got rick's ingredient 1 in the current dir
then the second ingredient in /home/rick/**

I suffered trying to get a reverse shell on this box only to figure out i can use sudo without a password

```
    sudo -l
```

#sudo picture#

flag at root



![pogge](imgs/ss.png)

https://www.makeareadme.com/