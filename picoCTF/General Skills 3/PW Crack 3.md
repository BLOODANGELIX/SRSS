## Descripción del reto
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución

- Descargar los 3 archivos y abrir el .py con nano.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.py
--2025-09-10 04:34:07--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.77, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                           100%[==================================================================>]   1.31K  --.-KB/s    in 0s      

2025-09-10 04:34:07 (847 MB/s) - 'level3.py' saved [1337/1337]

BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
--2025-09-10 04:34:23--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.72, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                 100%[==================================================================>]      31  --.-KB/s    in 0s      

2025-09-10 04:34:23 (7.56 MB/s) - 'level3.flag.txt.enc' saved [31/31]

BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
--2025-09-10 04:34:33--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.77, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                     100%[==================================================================>]      16  --.-KB/s    in 0s      

2025-09-10 04:34:33 (15.0 MB/s) - 'level3.hash.bin' saved [16/16]

BLOODANGELIX-picoctf@webshell:~$ ls
level3.flag.txt.enc  level3.hash.bin  level3.py
BLOODANGELIX-picoctf@webshell:~$ nano level3.py 
```

- Vemos que hay 7 contraseñas posibles.
```
import hashlib

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

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
```

- Intente una por una hasta encontrar la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{m45h_fl1ng1ng_cd6ed2eb}
## Notas
Se puede hacer de otra forma, haciendo un programa para que haga recursividad haciendo un archivo con codigo del archivo y ejecutandolo con el hash para que muestre la bandera.
```python
import hashlib

correct_pw_hash = open('level3.hash.bin', 'rb').read()

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

for pw in pos_pw_list:
    if hash_pw(pw) == correct_pw_hash:
        print("The password is: " + pw)
```

## Referencia
[Challenge 23: PW Crack 3 | ctf-writeups](https://ahmedheltaher.github.io/ctf-writeups/sites/picoCTF/General-Skills/PW-Crack-3.html)