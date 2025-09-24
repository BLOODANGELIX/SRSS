## Descripción del reto
There is some interesting information hidden around this site [http://mercury.picoctf.net:39698/](http://mercury.picoctf.net:39698/). Can you find it?

## Solución
- Empezamos en un sitio muy simple, el cual debemos de inspeccionar, y al inspeccionar notamos que en el código, esta la primera parte de la bandera e indica que busquemos las demás partes dentro de los archivos HTML, CSS y JavaScript.
![[Pasted image 20250923204659.png]]
![[Pasted image 20250923204754.png]]

- Luego nos vamos al CSS, donde esta la segunda parte de la bandera.
![[Pasted image 20250923204847.png]]

- Después nos vamos al JS, donde nos da una pista de lo que tenemos que hacer, y eso es irnos a la pagina principal y buscar el archivo `robots.txt`, ahi se encontrara la tercera parte de la bandera.
![[Pasted image 20250923205014.png]]

![[Pasted image 20250923205229.png]]

- La cuarta parte, aparecera si en lugar del archivo `robots.txt`, ponemos `.htacces`, que es un archivo que se encuentra dentro de Apache.
![[Pasted image 20250923205850.png]]

- Por ultimo buscamos un archivo que se encuentra dentro del contexto de la MAC, asi que en lugar de `.htacces` ahora pondremos `.DS_Store`.
![[Pasted image 20250923210151.png]]

## Notas


## Referencia