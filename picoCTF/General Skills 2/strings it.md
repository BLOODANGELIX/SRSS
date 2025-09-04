## Descripción del reto
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

## Solución
``` linux
BLOODANGELIX-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings 
--2025-09-03 16:39:33--  https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                             100%[==================================================================>] 757.84K  1.86MB/s    in 0.4s    

2025-09-03 16:39:34 (1.86 MB/s) - 'strings' saved [776032/776032]

BLOODANGELIX-picoctf@webshell:~$ ls
README.txt  strings
BLOODANGELIX-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_d66c7bb7}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{5tRIng5_1T_d66c7bb7}
## Notas
strings "nombre del archivo": muestra todas las cadenas sin caracteres especiales. 

Para cambiar los permisos a un archivo y hacerlo ejecutable:
```
BLOODANGELIX-picoctf@webshell:~$ chmod -x strings
BLOODANGELIX-picoctf@webshell:~$ ls -la strings
-rw-rw-r-- 1 BLOODANGELIX-picoctf BLOODANGELIX-picoctf 776032 Oct 26  2020 strings
BLOODANGELIX-picoctf@webshell:~$ chmod +x strings
BLOODANGELIX-picoctf@webshell:~$ ls -la strings
-rwxrwxr-x 1 BLOODANGELIX-picoctf BLOODANGELIX-picoctf 776032 Oct 26  2020 strings
BLOODANGELIX-picoctf@webshell:~$ 
```
## Referencia
