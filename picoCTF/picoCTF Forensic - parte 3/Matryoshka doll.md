## Descripción del reto
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg)

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ wget https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg              
--2025-10-14 15:58:49--  https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651632 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg                                       100%[====================================================================================================>] 636.36K  1.48MB/s    in 0.4s    

2025-10-14 15:58:50 (1.48 MB/s) - ‘dolls.jpg’ saved [651632/651632]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ file dolls.jpg   
dolls.jpg: PNG image data, 594 x 1104, 8-bit/color RGBA, non-interlaced

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ binwalk -e dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378952, uncompressed size: 383937, name: base_images/2_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ ls
dolls.jpg  _dolls.jpg.extracted

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ open dolls.jpg
  
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ cd _dolls.jpg.extracted 

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3/_dolls.jpg.extracted]
└─$ ls -la        
total 384
drwxrwxr-x 3 kali kali   4096 Oct 14 15:59 .
drwxrwxr-x 3 kali kali   4096 Oct 14 15:59 ..
-rw-rw-r-- 1 kali kali 379140 Oct 14 15:59 4286C.zip
drwxrwxr-x 2 kali kali   4096 Oct 14 15:59 base_images

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3/_dolls.jpg.extracted]
└─$ cd base_images         

┌──(kali㉿kali)-[~/…/Forensic/parte-3/_dolls.jpg.extracted/base_images]
└─$ ls -la                 
total 384
drwxrwxr-x 2 kali kali   4096 Oct 14 15:59 .
drwxrwxr-x 3 kali kali   4096 Oct 14 15:59 ..
-rw-r--r-- 1 kali kali 383937 Mar 15  2021 2_c.jpg

┌──(kali㉿kali)-[~/…/Forensic/parte-3/_dolls.jpg.extracted/base_images]
└─$ binwalk -e -M 2_c.jpg~  

General Error: Cannot open file 2_c.jpg~ (CWD: /home/kali/picoCTF/Forensic/parte-3/_dolls.jpg.extracted/base_images) : [Errno 2] No such file or directory: '2_c.jpg~'

┌──(kali㉿kali)-[~/…/Forensic/parte-3/_dolls.jpg.extracted/base_images]
└─$ binwalk -e -M 2_c.jpg 

Scan Time:     2025-10-14 16:01:42
Target File:   /home/kali/picoCTF/Forensic/parte-3/_dolls.jpg.extracted/base_images/2_c.jpg
MD5 Checksum:  5179dc878f273890194a56cf878d38c3
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


Scan Time:     2025-10-14 16:01:43
Target File:   /home/kali/picoCTF/Forensic/parte-3/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/3_c.jpg
MD5 Checksum:  8db9e80aa8b9e3b264e1e0e294efed5b
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77650, uncompressed size: 79807, name: base_images/4_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


Scan Time:     2025-10-14 16:01:43
Target File:   /home/kali/picoCTF/Forensic/parte-3/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/4_c.jpg
MD5 Checksum:  6ecfe874a2e3e07afb3d2b31abd72a1e
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 63, uncompressed size: 81, name: flag.txt

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


Scan Time:     2025-10-14 16:01:43
Target File:   /home/kali/picoCTF/Forensic/parte-3/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted/flag.txt
MD5 Checksum:  fa7951b35e25e9aef3fc424404ee742d
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------

┌──(kali㉿kali)-[~/…/Forensic/parte-3/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted 

┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls    
136DA.zip  flag.txt

┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt                                                                       
picoCTF{96fac089316e094d41ea046900197662}   
```

picoCTF{96fac089316e094d41ea046900197662}
## Notas


## Referencia