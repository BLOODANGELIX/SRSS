## Descripción del reto
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Solución
- Descargar el archivo en la consola
``` 
BLOODANGELIX-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file
--2025-09-01 17:05:51--  https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                  100%[=======================>]  14.21K  --.-KB/s    in 0s      

2025-09-01 17:05:51 (406 MB/s) - 'file' saved [14551/14551]
```

- Aplicar el comando wc para conocer la cantidad de lineas, caracteres y bytes, despues utilizar el comando grep para encontrar la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ wc file
    6   317 14551 file
BLOODANGELIX-picoctf@webshell:~$ grep 'picoCTF' file
picoCTF{grep_is_good_to_find_things_f77e0797}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{grep_is_good_to_find_things_f77e0797}
## Notas
wget : descargar archivos y contenido de internet.
wc : contar la cantidad de lineas, caracteres y bytes en ese orden.
grep : buscar dentro de un archivo.
## Referencia
[Wget - GNU Project - Free Software Foundation](https://www.gnu.org/software/wget/)
[Wc Command in Linux (Count Number of Lines, Words, and Characters) | Linuxize](https://linuxize.com/post/linux-wc-command/)
[Learn Grep and Regular Expressions with examples - Linux Tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)