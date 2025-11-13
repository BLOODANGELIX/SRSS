## Descripción del reto
What can you do with this file?I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/288/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ wget https://artifacts.picoctf.net/c/288/SafeOpener.class
--2025-11-12 12:07:46--  https://artifacts.picoctf.net/c/288/SafeOpener.class
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2036 (2.0K) [application/octet-stream]
Saving to: ‘SafeOpener.class’

SafeOpener.class                        100%[============================================================================>]   1.99K  --.-KB/s    in 0s      

2025-11-12 12:07:55 (63.1 MB/s) - ‘SafeOpener.class’ saved [2036/2036]

┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ strings -t x SafeOpener.class | grep picoCTF
    31d ,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}

```

picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}
## Notas


## Referencia
