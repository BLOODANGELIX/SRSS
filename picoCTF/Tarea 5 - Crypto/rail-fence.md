## Descripción del reto
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it?Download the message [here](https://artifacts.picoctf.net/c/189/message.txt).Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ wget https://artifacts.picoctf.net/c/189/message.txt  
--2025-11-08 13:40:30--  https://artifacts.picoctf.net/c/189/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 56 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                             100%[============================================================================>]      56  --.-KB/s    in 0s      

2025-11-08 13:40:30 (119 MB/s) - ‘message.txt’ saved [56/56]

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ cat message.txt                            
Ta _7N6D8Dhlg:W3D_H3C31N__387ef sHR053F38N43DFD i33___N6
```

![[Pasted image 20251108124637.png]]

picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_83F6D8D7}
## Notas


## Referencia
