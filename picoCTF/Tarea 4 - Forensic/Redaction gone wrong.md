## Descripción del reto
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Solución
- Descargamos y abrimos el archivo.
```
┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2025-10-25 16:16:21--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.64, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_Labs.pdf               100%[====================================================================================================>]  34.10K  --.-KB/s    in 0.003s  

2025-10-25 16:16:21 (10.6 MB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ open Financial_Report_for_ABC_Labs.pdf 

```

- Después simplemente seleccionamos todo el texto y nos dará la bandera
![[Pasted image 20251025141837.png]]

picoCTF{C4n_Y0u_S33_m3_fully}
## Notas


## Referencia
