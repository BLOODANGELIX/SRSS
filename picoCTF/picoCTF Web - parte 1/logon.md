## Descripción del reto
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796

## Solución
- En primera, se nos muestra un login para ingresar nuestros datos.
![[Pasted image 20250918195716.png]]

- Ingresamos nuestros un Username y un Password, y ahora nos muestra que no hay una bandera.
![[Pasted image 20250918195926.png]]

- Ahora nos metemos a las coockies, ya que hay se guardaron los registros de nuestro ingreso y notamos que no tenemos los permisos de `admin` a lo cual con una extensión, buscamos `admin` y lo cambiamos a `True`.
![[Pasted image 20250918200205.png]]

- Ahora si recargamos la pagina nos dará la bandera.

## Notas
Para resolverlo se descargo la extensión Cookie-Editor.

## Referencia
