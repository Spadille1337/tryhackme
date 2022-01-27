```bash
ssh barry@10.10.12.47 -i id_rsa
Enter passphrase for key 'id_rsa': 
Welcome to Ubuntu 16.04.7 LTS (GNU/Linux 4.4.0-210-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

34 packages can be updated.
16 of these updates are security updates.
To see these additional updates run: apt list --upgradable



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

barry@mustacchio:~$ ls -la
total 20
drwxr-xr-x 4 barry barry 4096 Jan 26 15:08 .
drwxr-xr-x 4 root  root  4096 Jun 12  2021 ..
drwx------ 2 barry barry 4096 Jan 26 15:08 .cache
drwxr-xr-x 2 barry barry 4096 Jun 12  2021 .ssh
-rw-r--r-- 1 barry barry   33 Jun 12  2021 user.txt
barry@mustacchio:~$ cat user.txt
62d77a4d5f97d47c5aa38b3b2651b831
```