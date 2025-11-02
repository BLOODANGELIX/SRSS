## Descripción del reto
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/hidetosee]
└─$ wget https://artifacts.picoctf.net/c/235/atbash.jpg 
--2025-11-02 14:15:28--  https://artifacts.picoctf.net/c/235/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51499 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                              100%[============================================================================>]  50.29K  --.-KB/s    in 0.09s   

2025-11-02 14:15:29 (578 KB/s) - ‘atbash.jpg’ saved [51499/51499]

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/hidetosee]
└─$ ls
atbash.jpg

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/hidetosee]
└─$ sudo apt install steghide 
[sudo] password for kali: 
The following packages were automatically installed and are no longer required:
  libbluray2       libgdata22     libogdi4.1          libsigsegv2        libtheora0     libudfread0            python3-wheel-whl
  libgdal36        libgeos3.13.1  libqt5ct-common1.8  libsoup-2.4-1      libtheoradec1  libvpx9
  libgdata-common  libhdf4-0-alt  libsframe1          libsoup2.4-common  libtheoraenc1  python3-packaging-whl
Use 'sudo apt autoremove' to remove them.

Installing:
  steghide

Installing dependencies:
  libmcrypt4  libmhash2

Suggested packages:
  libmcrypt-dev  mcrypt

Summary:
  Upgrading: 0, Installing: 3, Removing: 0, Not Upgrading: 921
  Download size: 309 kB
  Space needed: 907 kB / 57.9 GB available

Continue? [Y/n] Y
Get:1 http://kali.download/kali kali-rolling/main amd64 libmcrypt4 amd64 2.5.8-8 [72.2 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-10 [92.4 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 steghide amd64 0.5.1-15 [144 kB]
Fetched 309 kB in 1s (390 kB/s)   
Selecting previously unselected package libmcrypt4:amd64.
(Reading database ... 429710 files and directories currently installed.)
Preparing to unpack .../libmcrypt4_2.5.8-8_amd64.deb ...
Unpacking libmcrypt4:amd64 (2.5.8-8) ...
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack .../libmhash2_0.9.9.9-10_amd64.deb ...
Unpacking libmhash2:amd64 (0.9.9.9-10) ...
Selecting previously unselected package steghide.
Preparing to unpack .../steghide_0.5.1-15_amd64.deb ...
Unpacking steghide (0.5.1-15) ...
Setting up libmhash2:amd64 (0.9.9.9-10) ...
Setting up libmcrypt4:amd64 (2.5.8-8) ...
Setting up steghide (0.5.1-15) ...
Processing triggers for libc-bin (2.41-12) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.3.2) ...

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/hidetosee]
└─$ steghide steghide extract -sf atbash.jpg
steghide: unknown command "steghide".
steghide: type "steghide --help" for help.

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/hidetosee]
└─$ steghide extract -sf atbash.jpg         
Enter passphrase: 
wrote extracted data to "encrypted.txt".

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/hidetosee]
└─$ ls
atbash.jpg  encrypted.txt

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/hidetosee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_92533667}
```

![[Pasted image 20251102132217.png]]

picoCTF{atbash_crack_92533667}
## Notas


## Referencia
