## Descripción del reto
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg)

## Solución
- Descargamos la imagen y la abrimos con un editor de imagenes.
```
┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ wget https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg
--2025-10-25 14:38:53--  https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg                      100%[=============================================>] 857.55K  1.90MB/s    in 0.4s    

2025-10-25 14:38:54 (1.90 MB/s) - ‘cat.jpg’ saved [878136/878136]

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ open cat.jpg

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ gimp cat.jpg                               
set device 'ImExPS/2 Generic Explorer Mouse' to mode: disabled
set device 'Virtual core XTEST pointer' to mode: disabled
set device 'VirtualBox USB Tablet' to mode: disabled
set device 'VirtualBox mouse integration' to mode: disabled
[script-fu-test-sphere-v3] The catalog directory does not exist: /usr/lib/x86_64-linux-gnu/gimp/3.0/plug-ins/test-sphere-v3/locale
[script-fu-test-sphere-v3] Override method set_i18n() for the plug-in to customize or disable localization.
[script-fu-test-sphere-v3] Localization disabled
```

- Nos vamos a los metadatos y en la licencia encontraremos un cifrado en Base 64 a lo cual lo decodificaremos y obtendremos la bandera.
![[Pasted image 20251025135645.png]]
![[Pasted image 20251025140959.png]]

picoCTF{the_m3tadata_1s_modified}
## Notas


## Referencia
