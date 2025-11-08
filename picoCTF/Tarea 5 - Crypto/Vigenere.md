## Descripción del reto
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/160/cipher.txt) using this key "CYLAB".

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ wget https://artifacts.picoctf.net/c/160/cipher.txt 
--2025-11-08 13:57:43--  https://artifacts.picoctf.net/c/160/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt                              100%[============================================================================>]      43  --.-KB/s    in 0s      

2025-11-08 13:57:44 (111 MB/s) - ‘cipher.txt’ saved [43/43]

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}
```

![[Pasted image 20251108130446.png]]

picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}
## Notas


## Referencia
