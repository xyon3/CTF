# Teamfinal


================================================
## Nmap

TRY# 1 ----------- nmap -sS [ip] 

Starting Nmap 7.80 ( https://nmap.org ) at 2021-10-17 19:10 PST
Nmap scan report for 10.10.62.26 (10.10.62.26)
Host is up (0.41s latency).
Not shown: 997 filtered ports
PORT   STATE SERVICE
21/tcp open  ftp
22/tcp open  ssh
80/tcp open  http

Nmap done: 1 IP address (1 host up) scanned in 22.33 seconds

TRY #2 ----------- nmap -sV -sC [ip]

Starting Nmap 7.80 ( https://nmap.org ) at 2021-10-17 19:29 PST
Nmap scan report for 10.10.62.26 (10.10.62.26)
Host is up (0.40s latency).
Not shown: 997 filtered ports
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 79:5f:11:6a:85:c2:08:24:30:6c:d4:88:74:1b:79:4d (RSA)
|   256 af:7e:3f:7e:b4:86:58:83:f1:f6:a2:54:a6:9b:ba:ad (ECDSA)
|_  256 26:25:b0:7b:dc:3f:b2:94:37:12:5d:cd:06:98:c7:9f (ED25519)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: Apache2 Ubuntu Default Page: It works! If you see this add 'te...
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 40.90 seconds

=======================================================

DIRECTORY FOR http://team.thm

gobuster -w directory-list-lowercase-2.3-medium.txt

/images     >>>>> nothing useful
/scripts    >>>>> Forbiden >> enum4 interesting stuff
/assets     >>>>> Forbiden >> enum4 interesting stuff

nikto

/robots.txt >>>>> found username "dale"

