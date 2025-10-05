## Descripción del reto
Can you login to this website?Try to login [here](http://saturn.picoctf.net:49457/).

## Solución
- Al principio nos muestra una pagina en donde podemos hacer login.
![[Pasted image 20251004213335.png]]

- Al ingresar, vemos que nos muestra la sentencia SQL que podemos modificar al ingresar el usuario.
![[Pasted image 20251004213603.png]]

- Ahora ingresamos `admin' --` en el usuario y en password lo que queramos, con lo cual nos dejara ingresar de manera exitosa en la pagina, y por lo tanto en el código fuente se encontrara la bandera.
![[Pasted image 20251004213636.png]]

picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}
## Notas


## Referencia
