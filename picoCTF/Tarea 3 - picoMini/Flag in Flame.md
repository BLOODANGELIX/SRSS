## Descripción del reto
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log.Download the encoded data here: [Logs Data](https://challenge-files.picoctf.net/c_amiable_citadel/563936741f1fcad4b6e9e1043d56fd127ef7de2227d293a8e478ae6887816d10/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial .

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/concurso]
└─$ wget https://challenge-files.picoctf.net/c_amiable_citadel/563936741f1fcad4b6e9e1043d56fd127ef7de2227d293a8e478ae6887816d10/logs.txt
--2025-10-15 19:06:56--  https://challenge-files.picoctf.net/c_amiable_citadel/563936741f1fcad4b6e9e1043d56fd127ef7de2227d293a8e478ae6887816d10/logs.txt
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.125, 3.174.207.96, 3.174.207.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.125|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1592036 (1.5M) [application/octet-stream]
Saving to: ‘logs.txt’

logs.txt                                100%[============================================================================>]   1.52M  3.66MB/s    in 0.4s    

2025-10-15 19:06:57 (3.66 MB/s) - ‘logs.txt’ saved [1592036/1592036]

┌──(kali㉿kali)-[~/picoCTF/concurso]
└─$ xxd -l 300 logs.txt 
00000000: 6956 424f 5277 304b 4767 6f41 4141 414e  iVBORw0KGgoAAAAN
00000010: 5355 6845 5567 4141 4134 4141 4141 5341  SUhEUgAAA4AAAASA
00000020: 4341 4941 4141 4168 3862 534f 4141 4541  CAIAAAAh8bSOAAEA
00000030: 4145 6c45 5156 5234 6e4f 7a39 3139 4d73  AElEQVR4nOz919Ms
00000040: 795a 556e 6950 334f 6359 2b49 464a 2b36  yZUniP3OcY+IFJ+6
00000050: 6f75 7157 4271 6f61 7574 4459 526d 4e36  ouqWBqoautDYRmN6
00000060: 656d 6661 5a6d 6c63 306d 6932 2b37 7850  emfaZmlc0mi2+7xP
00000070: 4e4a 4a2f 474a 2f34 5276 4a74 4835 646d  NJJ/GJ/4RvJtH5dm
00000080: 5131 7662 4875 344d 7039 6b7a 6a51 5947  Q1vbHu4Mp9kzjQYG
00000090: 6f68 756f 416b 7268 3174 5766 7973 7949  ohuoAkrh1tWfysyI
000000a0: 6350 647a 2b48 4169 496a 3356 7036 366f  cPdz+HAiIj3Vp66o
000000b0: 616e 4873 326e 637a 4979 4d38 5842 3474  anHs2nczIyM8XB4t
000000c0: 3650 5550 2f69 3841 5345 4544 4b4b 6b71  6PUP/i8ASEEDKKkq
000000d0: 6951 4a51 7467 7367 496a 4255 4e57 6f55  iQJQtgsgIjBUNWoU
000000e0: 4553 4a31 7a6a 6b69 5655 5569 5a69 6279  ESJ1zjkiVUUiZiby
000000f0: 4968 4969 564e 5750 7075 5078 754a 784d  IhIiVNWPpuPxuJxM
00000100: 6971 4934 4f54 7435 3975 785a 5654 4952  iqI4OTt59uxZVTIR
00000110: 5561 7844 434a 5461 7738 4e44 5570 6e4e  UaxDCJTaw8NDUpnN
00000120: 5a6d 3164 3133 5874 3365 6a32            Zm1d13Xt3ej2

┌──(kali㉿kali)-[~/picoCTF/concurso]
└─$ base64 -d logs.txt > logs.png

┌──(kali㉿kali)-[~/picoCTF/concurso]
└─$ file logs.png               
logs.png: PNG image data, 896 x 1152, 8-bit/color RGB, non-interlaced

┌──(kali㉿kali)-[~/picoCTF/concurso]
└─$ open logs.png
```
![[Pasted image 20251015171331.png]]

- Decodificamos el texto en hexadecimal:
7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E675F35646161346132667D

picoCTF{forensics_analysis_is_amazing_5daa4a2f}

## Notas


## Referencia
