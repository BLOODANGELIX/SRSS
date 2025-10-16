## Descripción del reto
Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag?Download the [logs](https://challenge-files.picoctf.net/c_saffron_estate/3e417b56c25929c6c078813bba342ae27e2964223df8b72c4b67f65c876efa95/server.log) and figure out the full flag from the fragments.

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_saffron_estate/3e417b56c25929c6c078813bba342ae27e2964223df8b72c4b67f65c876efa95/server.log
--2025-10-15 17:14:57--  https://challenge-files.picoctf.net/c_saffron_estate/3e417b56c25929c6c078813bba342ae27e2964223df8b72c4b67f65c876efa95/server.log
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.18, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108322 (106K) [application/octet-stream]
Saving to: 'server.log'

server.log                          100%[==================================================================>] 105.78K  --.-KB/s    in 0.05s   

2025-10-15 17:14:57 (1.91 MB/s) - 'server.log' saved [108322/108322]

BLOODANGELIX-picoctf@webshell:~$ cat server.log | grep pico
[1990-08-09 10:00:10] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:04:27] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:04:29] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:04:37] INFO FLAGPART: picoCTF{us3_
[1990-08-09 12:19:23] INFO FLAGPART: picoCTF{us3_
[1990-08-09 12:19:29] INFO FLAGPART: picoCTF{us3_
[1990-08-09 12:19:32] INFO FLAGPART: picoCTF{us3_
BLOODANGELIX-picoctf@webshell:~$ cat server.log | grep FLAGPART
[1990-08-09 10:00:10] INFO FLAGPART: picoCTF{us3_
[1990-08-09 10:02:55] INFO FLAGPART: y0urlinux_
[1990-08-09 10:05:54] INFO FLAGPART: sk1lls_
[1990-08-09 10:05:55] INFO FLAGPART: sk1lls_
[1990-08-09 10:10:54] INFO FLAGPART: cedfa5fb}
[1990-08-09 10:10:58] INFO FLAGPART: cedfa5fb}
[1990-08-09 10:11:06] INFO FLAGPART: cedfa5fb}
[1990-08-09 11:04:27] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:04:29] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:04:37] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:09:16] INFO FLAGPART: y0urlinux_
[1990-08-09 11:09:19] INFO FLAGPART: y0urlinux_
[1990-08-09 11:12:40] INFO FLAGPART: sk1lls_
[1990-08-09 11:12:45] INFO FLAGPART: sk1lls_
[1990-08-09 11:16:58] INFO FLAGPART: cedfa5fb}
[1990-08-09 11:16:59] INFO FLAGPART: cedfa5fb}
[1990-08-09 11:17:00] INFO FLAGPART: cedfa5fb}
[1990-08-09 12:19:23] INFO FLAGPART: picoCTF{us3_
[1990-08-09 12:19:29] INFO FLAGPART: picoCTF{us3_
[1990-08-09 12:19:32] INFO FLAGPART: picoCTF{us3_
[1990-08-09 12:23:43] INFO FLAGPART: y0urlinux_
[1990-08-09 12:23:45] INFO FLAGPART: y0urlinux_
[1990-08-09 12:23:53] INFO FLAGPART: y0urlinux_
[1990-08-09 12:25:32] INFO FLAGPART: sk1lls_
[1990-08-09 12:28:45] INFO FLAGPART: cedfa5fb}
[1990-08-09 12:28:49] INFO FLAGPART: cedfa5fb}
[1990-08-09 12:28:52] INFO FLAGPART: cedfa5fb}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}
## Notas


## Referencia
