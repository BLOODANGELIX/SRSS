## Descripción del reto
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/3/challenge.zip)

The same files are accessible via SSH here:`ssh -p 53891 ctf-player@atlas.picoctf.net`Using the password `6dd28e9b`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ wget https://artifacts.picoctf.net/c_atlas/3/challenge.zip
--2025-10-25 16:30:07--  https://artifacts.picoctf.net/c_atlas/3/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 741 [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                                   100%[====================================================================================================>]     741  --.-KB/s    in 0s      

2025-10-25 16:30:07 (22.3 MB/s) - ‘challenge.zip’ saved [741/741]

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ ls
challenge.zip

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ unzip challenge.zip     
Archive:  challenge.zip
   creating: home/ctf-player/drop-in/
 extracting: home/ctf-player/drop-in/flag.png  

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ ls
challenge.zip  home

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ cd home/ctf-player/drop-in 

┌──(kali㉿kali)-[~/…/tarea_3/home/ctf-player/drop-in]
└─$ ls
flag.png

```

![[Pasted image 20251025143242.png]]

picoCTF{p33k_@_b00_a81f0a35}
## Notas


## Referencia
