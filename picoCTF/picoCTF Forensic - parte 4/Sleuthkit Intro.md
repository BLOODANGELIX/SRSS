## Descripción del reto
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)

Access checker program: `nc saturn.picoctf.net 62259`

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-intro]
└─$ wget https://artifacts.picoctf.net/c/164/disk.img.gz                                            
--2025-10-16 14:54:06--  https://artifacts.picoctf.net/c/164/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29714372 (28M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                                     100%[====================================================================================================>]  28.34M  5.88MB/s    in 4.8s    

2025-10-16 14:54:11 (5.85 MB/s) - ‘disk.img.gz’ saved [29714372/29714372]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-intro]
└─$ gzip -d disk.img.gz            

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-intro]
└─$ ls
disk.img

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-intro]
└─$ file disk.img 
disk.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0xc,190,50), startsector 2048, 202752 sectors

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-intro]
└─$ mmls disk.img     
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4/sleuth-intro]
└─$ nc saturn.picoctf.net 62259
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}

```

picoCTF{mm15_f7w!}
## Notas


## Referencia
