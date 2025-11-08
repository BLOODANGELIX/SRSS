## Descripción del reto
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar).The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ wget https://artifacts.picoctf.net/c/151/leak.tar
--2025-11-08 12:37:39--  https://artifacts.picoctf.net/c/151/leak.tar
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.26, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30720 (30K) [application/octet-stream]
Saving to: ‘leak.tar’

leak.tar                                100%[============================================================================>]  30.00K  --.-KB/s    in 0.003s  

2025-11-08 12:37:39 (10.5 MB/s) - ‘leak.tar’ saved [30720/30720]

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ tar -xvf leak.tar                                
leak/
leak/passwords.txt
leak/usernames.txt

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ cat leak/usernames.txt | grep -n "cultiris"     
378:cultiris

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ sed -n "378p" leak/passwords.txt
cvpbPGS{P7e1S_54I35_71Z3}

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ echo "cvpbPGS{P7e1S_54I35_71Z3}" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
picoCTF{C7r1F_54V35_71M3}

```

picoCTF{C7r1F_54V35_71M3}
## Notas


## Referencia
