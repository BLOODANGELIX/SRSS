## Descripción del reto
Morse code is well known. Can you decrypt this?Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ wget https://artifacts.picoctf.net/c/79/morse_chal.wav                                                                             
--2025-11-08 13:32:43--  https://artifacts.picoctf.net/c/79/morse_chal.wav
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.100, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2549024 (2.4M) [application/octet-stream]
Saving to: ‘morse_chal.wav’

morse_chal.wav                          100%[============================================================================>]   2.43M  11.0MB/s    in 0.2s    

2025-11-08 13:32:43 (11.0 MB/s) - ‘morse_chal.wav’ saved [2549024/2549024]

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ file morse_chal.wav 
morse_chal.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 44100 Hz
```

![[Pasted image 20251108123641.png]]

picoCTF{wh47_h47h_90d_w20u9h7}
## Notas


## Referencia
