## Descripción del reto
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/23/convertme.py)
## Solución

Descargar el archivo y correrlo con python.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/23/convertme.py
--2025-09-10 02:56:32--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.77, 3.170.131.33, 3.170.131.72, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.77|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py          100%[=======================>]   1.16K  --.-KB/s    in 0s      

2025-09-10 02:56:32 (26.6 MB/s) - 'convertme.py' saved [1189/1189]

BLOODANGELIX-picoctf@webshell:~$ python3 convertme.py 
If 91 is in decimal base, what is it in binary base?
```

Tendremos que entrar en la terminal de python para utilizar bin para convertir el decimal a binario y obtener la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(91)
'0b1011011'
>>> 
```

La metemos en la respuesta y nos dará la bandera.
```
Answer: 01011011
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
```

picoCTF{4ll_y0ur_b4535_9c3b7d4d}
## Notas


## Referencia