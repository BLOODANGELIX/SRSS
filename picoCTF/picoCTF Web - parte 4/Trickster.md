## Descripción del reto
I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:63141/)!

## Solución
- Al principio nos muestra esta pagina, en la cual podemos subir imágenes PNG.
![[Pasted image 20250930224851.png]]

- Buscamos en donde se almacenan las imágenes, a lo cual ingresamos con un `sobots.txt` con el cual nos saldrán una serie de instrucciones, las cuales nos indican en que carpeta se almacenan las imágenes, con esto en mente, procedemos a hacer un script php que se ejecute en la pagina y así explotar su vulnerabilidad.
![[Pasted image 20250930225632.png]]
![[Pasted image 20250930230311.png]]

- Esto es lo que tiene que contener el archivo `php`.
![[Pasted image 20250930225723.png]]

- Ahora lo subimos y ejecutamos el `webshell.php.png`, este se ejecuta en la pagina `unloads` en donde se sube todo archivo que carguemos en esta pagina. En la URL, empezamos posicionándonos en la carpeta `uploads` de ahí, buscamos el archivo que subimos, después vemos la lista de archivos un directorio antes de `uploads` y ahí nos encontraremos un archivo raro el cual veremos su contenido y ahí estará la bandera.
![[Pasted image 20250930225950.png]]
![[Pasted image 20250930231057.png]]
![[Pasted image 20250930230806.png]]
![[Pasted image 20250930231022.png]]
![[Pasted image 20250930231039.png]]

picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_73198bd9}
## Notas


## Referencia