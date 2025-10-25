## Descripción del reto
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/260/flag.png).

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ wget https://artifacts.picoctf.net/c/260/flag.png                        
--2025-10-25 16:20:15--  https://artifacts.picoctf.net/c/260/flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43005 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                                        100%[====================================================================================================>]  42.00K  --.-KB/s    in 0.05s   

2025-10-25 16:20:16 (781 KB/s) - ‘flag.png’ saved [43005/43005]

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ binwalk flag.png             

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2944, uncompressed size: 3095, name: secret/flag.png
42983         0xA7E7          End of Zip archive, footer length: 22


┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2944, uncompressed size: 3095, name: secret/flag.png

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ ls
cat.jpg  Financial_Report_for_ABC_Labs.pdf  flag.png  _flag.png.extracted  pico.flag.png

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ cd _flag.png.extracted 

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3/_flag.png.extracted]
└─$ ls
29  29.zlib  9B3B.zip  secret

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3/_flag.png.extracted]
└─$ cd secret             

┌──(kali㉿kali)-[~/…/Forensic/tarea_3/_flag.png.extracted/secret]
└─$ ls
flag.png

┌──(kali㉿kali)-[~/…/Forensic/tarea_3/_flag.png.extracted/secret]
└─$ open flag.png                         

```

![[Pasted image 20251025142406.png]]

picoCTF{Hiddinng_An_imag3_within_@n_ima9e_ad9f6587}
## Notas


## Referencia
