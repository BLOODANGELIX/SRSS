## Descripción del reto
Can you get the flag?Go to this [website](http://saturn.picoctf.net:57168/) and see what you can discover.

## Solución
- Nos muestra la pagina principal, la cual nos pide que ingresemos un usuario y contraseña.
![[Pasted image 20251004202409.png]]

- Ahora como no nos deja acceder, entramos a inspeccionar el código fuente. En el código nos vamos a la pestaña network y vemos que hay un archivo llamado `secure.js` en el cual encontraremos el usuario y la contraseña.
![[Pasted image 20251004202525.png]]
![[Pasted image 20251004202546.png]]

- Una vez ingresados nos dará la bandera.
![[Pasted image 20251004202621.png]]
![[Pasted image 20251004202632.png]]

picoCTF{j5_15_7r4n5p4r3n7_a8788e61}
## Notas


## Referencia
