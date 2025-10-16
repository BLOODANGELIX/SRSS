## Descripción del reto
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/137/disk.flag.img.gz)

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ wget https://artifacts.picoctf.net/c/137/disk.flag.img.gz
--2025-10-16 15:02:09--  https://artifacts.picoctf.net/c/137/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 47534568 (45M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz                                100%[====================================================================================================>]  45.33M  3.98MB/s    in 11s     

2025-10-16 15:02:21 (4.00 MB/s) - ‘disk.flag.img.gz’ saved [47534568/47534568]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ ls
disk.flag.img.gz

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ gzip -d disk.flag.img.gz 

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ ls
disk.flag.img

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ mmls disk.flag.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ fls -o 2048 disk.flag.img 
d/d 11: lost+found
r/r 12: ldlinux.sys
r/r 13: ldlinux.c32
r/r 15: config-virt
r/r 16: vmlinuz-virt
r/r 17: initramfs-virt
l/l 18: boot
r/r 20: libutil.c32
r/r 19: extlinux.conf
r/r 21: libcom32.c32
r/r 22: mboot.c32
r/r 23: menu.c32
r/r 14: System.map-virt
r/r 24: vesamenu.c32
V/V 25585:      $OrphanFiles

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ fls -o 360448 -r disk.flag.img
d/d 451:        home
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
+ r/r 23:       group
+ r/r 24:       group-
+ r/r 25:       shadow
+ r/r 26:       shadow-
+ r/r 27:       passwd
+ r/r 28:       passwd-
+ r/r 29:       hosts
+ d/d 30:       zoneinfo
++ r/r 31:      UTC
+ r/r * 32(realloc):    resolv.conf
+ d/d 33:       keymap
++ r/r 34:      us.bmap.gz
+ r/r 35:       inittab
+ d/d 36:       conf.d
.......

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ fls -o 360448 -r disk.flag.img 2371
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 2371
)

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-app]
└─$ icat -o 360448 -r disk.flag.img 2371
picoCTF{by73_5urf3r_adac6cb4}

```

picoCTF{by73_5urf3r_adac6cb4}
## Notas


## Referencia
