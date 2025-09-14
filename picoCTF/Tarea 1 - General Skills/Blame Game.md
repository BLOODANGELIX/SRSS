## Descripción del reto
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/73/challenge.zip)

## Solución

Descargamos el archivo, los descomprimimos, accedemos al directorio descomprimido y aplicamos *git blame message.py* para ver quien fue el ultimo que modifico el archivo.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/73/challenge.zip
--2025-09-14 06:05:48--  https://artifacts.picoctf.net/c_titan/73/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.77, 3.170.131.72, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 293493 (287K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                       100%[==================================================================>] 286.61K  1.85MB/s    in 0.2s    

2025-09-14 06:05:48 (1.85 MB/s) - 'challenge.zip' saved [293493/293493]

BLOODANGELIX-picoctf@webshell:~$ ls
challenge.zip
BLOODANGELIX-picoctf@webshell:~$ unzip challenge.zip

BLOODANGELIX-picoctf@webshell:~$ cd drop-in/
BLOODANGELIX-picoctf@webshell:~/drop-in$ git log
BLOODANGELIX-picoctf@webshell:~/drop-in$ ls
message.py
BLOODANGELIX-picoctf@webshell:~/drop-in$ python3 message.py 
  File "/home/BLOODANGELIX-picoctf/drop-in/message.py", line 1
    print("Hello, World!"
         ^
SyntaxError: '(' was never closed
BLOODANGELIX-picoctf@webshell:~/drop-in$ git blame message.py

picoCTF{@sk_th3_1nt3rn_e9957ce1}

[9]+  Stopped                 git blame message.py
```

picoCTF{@sk_th3_1nt3rn_e9957ce1}
## Notas
git blame message.py: sirve para **ver línea por línea quién fue el último autor que modificó cada parte del archivo `message.py`**, junto con el **commit**, la **fecha** y el **contenido** de la línea.

## Referencia
