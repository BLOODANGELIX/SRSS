## Descripción del reto
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:53478/) out.

## Solución
- Al comienzo nos muestra la pagina principal.
![[Pasted image 20251004204655.png]]

- Buscamos el archivo `robots.txt`, el cual nos da una codificación en Base64, lo decodificamos con cualquier decodificador y nos da `js/myfile.txt`.
![[Pasted image 20251004204736.png]]

- Entramos al archivo `js/myfile.txt` y ahi estará la bandera.
![[Pasted image 20251004204759.png]]

picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}

## Notas


## Referencia
