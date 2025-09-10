## Descripción del reto
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

## Solución

- Descargamos los dos archivos, corremos el archivo .py, pero al no tener la contraseña nos salimos y utilizamos nano para ingresar al codigo.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.py
--2025-09-10 04:07:37--  https://artifacts.picoctf.net/c/10/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.77, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                           100%[==================================================================>]     876  --.-KB/s    in 0s      

2025-09-10 04:07:37 (264 MB/s) - 'level1.py' saved [876/876]

BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
--2025-09-10 04:07:52--  https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.72, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                 100%[==================================================================>]      30  --.-KB/s    in 0s      

2025-09-10 04:07:52 (17.4 MB/s) - 'level1.flag.txt.enc' saved [30/30]

BLOODANGELIX-picoctf@webshell:~$ ls
README.txt  level1.flag.txt.enc  level1.py

BLOODANGELIX-picoctf@webshell:~$ python3 level1.py 
Please enter correct password for flag: ^CTraceback (most recent call last):
  File "/home/BLOODANGELIX-picoctf/level1.py", line 28, in <module>
    level_1_pw_check()
  File "/home/BLOODANGELIX-picoctf/level1.py", line 18, in level_1_pw_check
    user_pw = input("Please enter correct password for flag: ")
KeyboardInterrupt

BLOODANGELIX-picoctf@webshell:~$ nano level1.py
```

- Dentro del codigo podemos ver que hay un apartado que indica la constraseña que debemos ingresar en la ejecucion del .py.
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


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "691d"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
```

- La ingresamos y nos da la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ python3 level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{545h_r1ng1ng_56891419}
## Notas


## Referencia