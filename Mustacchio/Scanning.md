```bash
nmap -sC -sV 10.10.159.49
Starting Nmap 7.92 ( https://nmap.org ) at 2022-01-25 09:52 EST
Nmap scan report for 10.10.159.49
Host is up (0.19s latency).
Not shown: 998 filtered tcp ports (no-response)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 58:1b:0c:0f:fa:cf:05:be:4c:c0:7a:f1:f1:88:61:1c (RSA)
|   256 3c:fc:e8:a3:7e:03:9a:30:2c:77:e0:0a:1c:e4:52:e6 (ECDSA)
|_  256 9d:59:c6:c7:79:c5:54:c4:1d:aa:e4:d1:84:71:01:92 (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
| http-robots.txt: 1 disallowed entry 
|_/
|_http-title: Mustacchio | Home
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

```bash
nmap -sC -sV -p 1001-10000 10.10.159.49
Starting Nmap 7.92 ( https://nmap.org ) at 2022-01-25 10:12 EST
Nmap scan report for 10.10.159.49
Host is up (0.16s latency).
Not shown: 8999 filtered tcp ports (no-response)
PORT     STATE SERVICE VERSION
8765/tcp open  http    nginx 1.10.3 (Ubuntu)
|_http-title: Mustacchio | Login
|_http-server-header: nginx/1.10.3 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

