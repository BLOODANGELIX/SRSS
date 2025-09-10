## Descripción del reto
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)

## Solución

- Descargar el archivo y ver el archivo a través de nano.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/27/fixme1.py
--2025-09-10 03:08:30--  https://artifacts.picoctf.net/c/27/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                           100%[==================================================================>]     837  --.-KB/s    in 0s      

2025-09-10 03:08:30 (43.4 MB/s) - 'fixme1.py' saved [837/837]

BLOODANGELIX-picoctf@webshell:~$ nano fixme1.py

```

- Corregir el codigo
```
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) +>

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)
```

- Correr el archivo ya corregido
```
BLOODANGELIX-picoctf@webshell:~$ python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{1nd3nt1ty_cr1515_182342f7}
## Notas
nano: sirve para ver y corregir el código fuente de un archivo.

## Referencia