## Descripción del reto
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag).
## Solución

``` 
BLOODANGELIX-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
--2025-09-01 17:16:20--  https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                  100%[=======================>]      34  --.-KB/s    in 0s      

2025-09-01 17:16:20 (20.9 MB/s) - 'flag' saved [34/34]

BLOODANGELIX-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_f28ac910}
```
## Notas
cat: permite mostrar el contenido del archivo.

## Referencia
[Comando cat de Linux: para qué sirve y ejemplos de uso](https://www.hostinger.com/es/tutoriales/comando-cat-linux)