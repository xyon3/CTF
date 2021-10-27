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


```bash
[IPADDR]:80

    from '/index.html' source
         <!--

             Note to self, remember username!

             Username: R1ckRul3s

          -->

    in '/login.php'
        username: R1ckRul3s
        password: Wubbalubbadubdub

    LOGGED IN '/portal.php'
            PORTAL.PHP can execute code but w/ limitations

            with 'ls'
                drwxr-xr-x 3 root   root   4096 Feb 10  2019 .
                drwxr-xr-x 3 root   root   4096 Feb 10  2019 ..
                -rwxr-xr-x 1 ubuntu ubuntu   17 Feb 10  2019 Sup3rS3cretPickl3Ingred.txt
                drwxrwxr-x 2 ubuntu ubuntu 4096 Feb 10  2019 assets
                -rwxr-xr-x 1 ubuntu ubuntu   54 Feb 10  2019 clue.txt
                -rwxr-xr-x 1 ubuntu ubuntu 1105 Feb 10  2019 denied.php
                -rwxrwxrwx 1 ubuntu ubuntu 1062 Feb 10  2019 index.html
                -rwxr-xr-x 1 ubuntu ubuntu 1438 Feb 10  2019 login.php
                -rwxr-xr-x 1 ubuntu ubuntu 2044 Feb 10  2019 portal.php
                -rwxr-xr-x 1 ubuntu ubuntu   17 Feb 10  2019 robots.txt

            can use python3
                'python3 -m http.server 8000'

            YOU CAN USE 'LESS' PAUL U STUPID FUCK!


            

        source code: found 'Vm1wR1UxTnRWa2RUV0d4VFlrZFNjRlV3V2t0alJsWnlWbXQwVkUxV1duaFZNakExVkcxS1NHVkliRmhoTVhCb1ZsWmFWMVpWTVVWaGVqQT0=='
        decoded several times to rabbit 'hole'




```




```
FROM ANOTHER WRITE-UP
    /login.php found from nikto (but my nikto scan failed to see it)
```

