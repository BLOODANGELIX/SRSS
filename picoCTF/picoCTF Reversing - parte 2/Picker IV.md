## Descripción del reto
Can you figure out how this program works to get the flag?

Connect to the program with netcat:`$ nc saturn.picoctf.net 53252`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV).
## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ wget https://artifacts.picoctf.net/c/527/picker-IV
--2025-11-12 11:37:33--  https://artifacts.picoctf.net/c/527/picker-IV
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17272 (17K) [application/octet-stream]
Saving to: ‘picker-IV’

picker-IV                               100%[============================================================================>]  16.87K  --.-KB/s    in 0s      

2025-11-12 11:37:33 (55.0 MB/s) - ‘picker-IV’ saved [17272/17272]

```

```Python
from pwn import *
elf = ELF('./picker-IV')
r = remote('saturn.picoctf.net', 58129)
r.sendlineafter(b': ', hex(elf.symbols['win'])[2:])
print(r.recvall().decode())
```

```bash
┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ /bin/python /home/kali/picoCTF/reversing/parte-2/sl.py
[*] '/home/kali/picoCTF/reversing/parte-2/picker-IV'
    Arch:       amd64-64-little
    RELRO:      Partial RELRO
    Stack:      No canary found
    NX:         NX enabled
    PIE:        No PIE (0x400000)
    SHSTK:      Enabled
    IBT:        Enabled
    Stripped:   No
[+] Opening connection to saturn.picoctf.net on port 58129: Done
/home/kali/picoCTF/reversing/parte-2/sl.py:4: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendlineafter(b': ', hex(elf.symbols['win'])[2:])
[+] Receiving all data: Done (84B)
[*] Closed connection to saturn.picoctf.net port 58129
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_01672a61}
```

picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_01672a61}
## Notas


## Referencia

