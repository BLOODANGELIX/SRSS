## Descripción del reto
How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/4/unknown.zip).

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ wget https://artifacts.picoctf.net/c_titan/4/unknown.zip  
--2025-10-25 17:30:42--  https://artifacts.picoctf.net/c_titan/4/unknown.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.61, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2252173 (2.1M) [application/octet-stream]
Saving to: ‘unknown.zip’

unknown.zip                                     100%[====================================================================================================>]   2.15M  6.11MB/s    in 0.4s    

2025-10-25 17:30:43 (6.11 MB/s) - ‘unknown.zip’ saved [2252173/2252173]

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ unzip unknown.zip  
Archive:  unknown.zip
  inflating: ukn_reality.jpg         

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ ls
ukn_reality.jpg  unknown.zip

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ strings ukn_reality.jpg 
JFIF
7http://ns.adobe.com/xap/1.0/
<?xpacket begin='
' id='W5M0MpCehiHzreSzNTczkc9d'?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='Image::ExifTool 11.88'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>
 <rdf:Description rdf:about=''
  xmlns:cc='http://creativecommons.org/ns#'>
  <cc:attributionURL rdf:resource='cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg=='/>
 </rdf:Description>
</rdf:RDF>
</x:xmpmeta>

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ echo cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg== | base64 -d                               
picoCTF{ME74D47A_HIDD3N_deca06fb}

```

picoCTF{ME74D47A_HIDD3N_deca06fb}
## Notas


## Referencia
