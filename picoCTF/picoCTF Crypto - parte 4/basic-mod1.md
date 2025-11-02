## Descripción del reto
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/128/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/basic-mod1]
└─$ wget https://artifacts.picoctf.net/c/128/message.txt                                   
--2025-11-02 14:08:48--  https://artifacts.picoctf.net/c/128/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 84 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                             100%[============================================================================>]      84  --.-KB/s    in 0s      

2025-11-02 14:08:49 (170 MB/s) - ‘message.txt’ saved [84/84]

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/basic-mod1]
└─$ strings message.txt            
165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138 
```

```python
from string import ascii_uppercase
x = [165, 248, 94, 346, 299, 73, 198, 221, 313, 137, 205,
87, 336, 110, 186, 69, 223, 213, 216, 216, 177, 138]

a = ascii_uppercase + "0123456789_"

for i in x:
	print(a[i % 37], end="")
```

```bash
┌──(kali㉿kali)-[~/Desktop]
└─$ /bin/python /home/kali/picoCTF/crypto/parte-4/basic-mod1/basic-mod1.py
R0UND_N_R0UND_B6B25531
```

picoCTF{R0UND_N_R0UND_B6B25531}
## Notas


## Referencia
