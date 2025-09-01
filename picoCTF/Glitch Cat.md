## Descripción del reto
Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.
## Solución

- Conectarse a la dirección a través de su puerto.
```
BLOODANGELIX-picoctf@webshell:~$ nc saturn.picoctf.net 53893
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
^C
```
- Pasar la salida a python para transformar a una salida legible.
```
BLOODANGELIX-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
'picoCTF{gl17ch_m3_n07_a4392d2e}'
```
## Notas
Me ayudo la Vale.

## Referencia