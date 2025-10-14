## Descripción del reto
We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ wget https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n
--2025-10-14 16:07:49--  https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: ‘tunn3l_v1s10n’

tunn3l_v1s10n                                   100%[====================================================================================================>]   2.76M  2.38MB/s    in 1.2s    

2025-10-14 16:07:51 (2.38 MB/s) - ‘tunn3l_v1s10n’ saved [2893454/2893454]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ file tunn3l_v1s10n 
tunn3l_v1s10n: data

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ xxd -g 1 tunn3l_v1s10n | head
00000000: 42 4d 8e 26 2c 00 00 00 00 00 ba d0 00 00 ba d0  BM.&,...........
00000010: 00 00 6e 04 00 00 32 01 00 00 01 00 18 00 00 00  ..n...2.........
00000020: 00 00 58 26 2c 00 25 16 00 00 25 16 00 00 00 00  ..X&,.%...%.....
00000030: 00 00 00 00 00 00 23 1a 17 27 1e 1b 29 20 1d 2a  ......#..'..) .*
00000040: 21 1e 26 1d 1a 31 28 25 35 2c 29 33 2a 27 38 2f  !.&..1(%5,)3*'8/
00000050: 2c 2f 26 23 33 2a 26 2d 24 20 3b 32 2e 32 29 25  ,/&#3*&-$ ;2.2)%
00000060: 30 27 23 33 2a 26 38 2c 28 36 2b 27 39 2d 2b 2f  0'#3*&8,(6+'9-+/
00000070: 26 23 1d 12 0e 23 17 11 29 16 0e 55 3d 31 97 76  &#...#..)..U=1.v
00000080: 66 8b 66 52 99 6d 56 9e 70 58 9e 6f 54 9c 6f 54  f.fR.mV.pX.oT.oT
00000090: ab 7e 63 ba 8c 6d bd 8a 69 c8 97 71 c1 93 71 c1  .~c..m..i..q..q.

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ mv tunn3l_v1s10n tunn3l_v1s10n.bmp

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ ls
tunn3l_v1s10n.bmp

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ exiftool tunn3l_v1s10n.bmp        
ExifTool Version Number         : 13.25
File Name                       : tunn3l_v1s10n.bmp
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2021:03:15 14:24:47-04:00
File Access Date/Time           : 2025:10:14 16:07:56-04:00
File Inode Change Date/Time     : 2025:10:14 16:09:42-04:00
File Permissions                : -rw-rw-r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Unknown (53434)
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Red Mask                        : 0x27171a23
Green Mask                      : 0x20291b1e
Blue Mask                       : 0x1e212a1d
Alpha Mask                      : 0x311a1d26
Color Space                     : Unknown (,5%()
Rendering Intent                : Unknown (826103054)
Image Size                      : 1134x306
Megapixels                      : 0.347

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ stat tunn3l_v1s10n.bmp | grep Size
  Size: 2893454         Blocks: 5656       IO Block: 4096   regular file
  
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ hexeditor tunn3l_v1s10n.bm
```

```
File: tunn3l_v1s10n.bmp                                                                                                                        ASCII Offset: 0x00000000 / 0x002C268D (%00)   
00000000  42 4D 8E 26  2C 00 00 00   00 00 BA D0  00 00 BA D0                                                                                                                BM.&,...........
00000010  00 00 6E 04  00 00 E8 03   00 00 01 00  18 00 00 00                                                                                                                ..n.............
00000020  00 00 58 26  2C 00 25 16   00 00 25 16  00 00 00 00 
```

- Abrimos la imagen.
![[Pasted image 20251014142305.png]]

picoCTF{qu1t3_a_v13w_2020}
## Notas


## Referencia