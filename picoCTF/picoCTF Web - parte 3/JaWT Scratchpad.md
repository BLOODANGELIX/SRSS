## Descripción del reto
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

## Solución
- Al inicio nos muestra una pagina en la cual pondremos nuestro nombre, ya que ingresar `admin`
no nos dejara porque necesita permisos especiales.
![[Pasted image 20250925201846.png]]

- Después notamos que en las cookies guardadas esta una llamada `jwt`, con la cual copiaremos su token y lo pondremos en un archivo.
![[Pasted image 20250925202011.png]]

- Para guardarlo, utilizamos el comando `nano`, ingresamos el token copiado en el archivo creado con `nano`, y lo guardamos. Lo siguiente es buscar en la dirección `usr\share\wordlists` un archivo llamado `rockyou`, con el cual se usara para encontrar la bandera, lo desempaquetamos y luego instalamos `Jhon the Ripper`, ya ejecutado con nuestro token, nos dará una frase que usaremos en el token..
![[Pasted image 20250925203639.png]]![[Pasted image 20250925203848.png]]

- Después nos iremos a una pagina `https://jwt.lannysport.net/`, con la cual podremos modificar el token para que nos de la bandera.
![[Pasted image 20250925204049.png]]

- Una vez modificado el token, regresamos a la pagina y pegamos el token justo en donde sacamos el original y le damos guardar, recargamos la pagina y ya estará la bandera.
![[Pasted image 20250925204144.png]]
![[Pasted image 20250925204207.png]]


## Notas


## Referencia