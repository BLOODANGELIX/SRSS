## Descripción del reto
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm) has extraordinarily helpful information...

## Solución
```
BLOODANGELIX-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
--2025-09-03 16:51:42--  https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                100%[==================================================================>]  10.68K  --.-KB/s    in 0s      

2025-09-03 16:51:42 (117 MB/s) - 'warm' saved [10936/10936]

BLOODANGELIX-picoctf@webshell:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=01b148cdedfc38125cac0d87e0537466d47927b1, with debug_info, not stripped

BLOODANGELIX-picoctf@webshell:~$ chmod +x warm
BLOODANGELIX-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!

BLOODANGELIX-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
```

picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
## Notas
chmod +x "nombre del archivo" : da los privilegios al archivo para poder ejecutarlo.

./"nombre del archivo" : este comando sirve para si el archivo es ejecutable poder ejecutar el archivo.

## Referencia