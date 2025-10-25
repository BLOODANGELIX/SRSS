## Descripción del reto
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf).

## Solución
- Descargamos y abrimos el archivo, el cual solo contiene una parte de la bandera.
```bash
┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ wget https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf
--2025-10-25 17:35:41--  https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.100, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3362 (3.3K) [application/octet-stream]
Saving to: ‘flag2of2-final.pdf’

flag2of2-final.pdf                              100%[====================================================================================================>]   3.28K  --.-KB/s    in 0s      

2025-10-25 17:35:41 (102 MB/s) - ‘flag2of2-final.pdf’ saved [3362/3362]

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ open flag2of2-final.pdf 
```

- A lo que iremos a una pagina para reparar el PDF, pasamos el PDF a esta pagina y nos dará un archivo, con la primera parte de la bandera. Asi juntando las dos partes obtendremos la bandera.
![[Pasted image 20251025154222.png]]
![[Pasted image 20251025154242.png]]

picoCTF{f1u3n7_1n_pn9_&_pdf_90974127}
## Notas


## Referencia
