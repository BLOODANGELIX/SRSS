## Descripción del reto
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.

## Solución
- Descargamos la imagen y realizamos un `cat`, la bandera se encontrara en la parte inferior antes de la linea de comandos.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
--2025-10-03 03:00:00--  https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: 'garden.jpg.1'

garden.jpg.1                        100%[==================================================================>]   2.19M  1.82MB/s    in 1.2s    

2025-10-03 03:00:01 (1.82 MB/s) - 'garden.jpg.1' saved [2295192/2295192]

BLOODANGELIX-picoctf@webshell:~$ cat garden.jpg 


  ?/\qZfd4Հ<?,ϺQ\u%Kɩn~O)YҾq}}et#?njo        o+]zQOhVcK+{YIK>^0`0GֺXF<j~kVy9S 1uӲHere is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
BLOODANGELIX-picoctf@webshell:~$ 
```
## Notas


## Referencia
