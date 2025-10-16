## Descripción del reto
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/920731987787c93839776ce457d5ecd6/dds1-alpine.flag.img.gz)

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/disk-disk-sleuth]
└─$ wget https://mercury.picoctf.net/static/920731987787c93839776ce457d5ecd6/dds1-alpine.flag.img.gz
--2025-10-16 14:41:11--  https://mercury.picoctf.net/static/920731987787c93839776ce457d5ecd6/dds1-alpine.flag.img.gz
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29768910 (28M) [application/octet-stream]
Saving to: ‘dds1-alpine.flag.img.gz’

dds1-alpine.flag.img.gz                         100%[====================================================================================================>]  28.39M  4.24MB/s    in 8.4s    

2025-10-16 14:41:20 (3.39 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768910/29768910]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/disk-disk-sleuth]
└─$ gzip -d dds1-alpine.flag.img.gz           

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/disk-disk-sleuth]
└─$ ls
dds1-alpine.flag.img

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/disk-disk-sleuth]
└─$ sudo apt install -y sleuthkit
sleuthkit is already the newest version (4.12.1+dfsg-0kali6).
sleuthkit set to manually installed.
The following packages were automatically installed and are no longer required:
  libbluray2  libgdata-common  libgeos3.13.1  libogdi4.1          libsframe1   libsoup-2.4-1      libtheora0     libtheoraenc1  libvpx9                python3-wheel-whl
  libgdal36   libgdata22       libhdf4-0-alt  libqt5ct-common1.8  libsigsegv2  libsoup2.4-common  libtheoradec1  libudfread0    python3-packaging-whl
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 0

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/disk-disk-sleuth]
└─$ srch_strings dds1-alpine.flag.img | grep pico
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_564ff1a0}

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/disk-disk-sleuth]
└─$ 

```

picoCTF{f0r3ns1c4t0r_n30phyt3_564ff1a0}
## Notas


## Referencia
