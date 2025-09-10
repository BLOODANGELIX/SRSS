## Descripción del reto
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.

## Solución

- Descargamos los dos archivos, y corremos el .py, para darnos cuenta que pide una contraseña, por lo tanto usamos nano para ver el código fuente.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.py
--2025-09-10 04:22:16--  https://artifacts.picoctf.net/c/14/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                           100%[==================================================================>]     914  --.-KB/s    in 0s      

2025-09-10 04:22:17 (173 MB/s) - 'level2.py' saved [914/914]

BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
--2025-09-10 04:22:29--  https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.77, 3.170.131.33, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.77|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                 100%[==================================================================>]      31  --.-KB/s    in 0s      

2025-09-10 04:22:29 (13.7 MB/s) - 'level2.flag.txt.enc' saved [31/31]

BLOODANGELIX-picoctf@webshell:~$ ls
level2.flag.txt.enc  level2.py
BLOODANGELIX-picoctf@webshell:~$ python3 level2.py 
Please enter correct password for flag: ^CTraceback (most recent call last):
  File "/home/BLOODANGELIX-picoctf/level2.py", line 27, in <module>
    level_2_pw_check()
  File "/home/BLOODANGELIX-picoctf/level2.py", line 17, in level_2_pw_check
    user_pw = input("Please enter correct password for flag: ")
KeyboardInterrupt

BLOODANGELIX-picoctf@webshell:~$ nano level2.py
```

- La contraseña esta en "user_pw" y vemos que esta en hexadecimal, por lo tanto la copiamos y nos salimos del nano.
```
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
```

- Ingresamos en python y pegamos la llave para que las funciones la conviertan a ASCII.
```
BLOODANGELIX-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
'4ec9'
>>> exit()
```

- Con la contraseña correcta ahora si corremos el .py, ingresamos la contraseña y nos da la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ python3 level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{tr45h_51ng1ng_9701e681}
## Notas


## Referencia