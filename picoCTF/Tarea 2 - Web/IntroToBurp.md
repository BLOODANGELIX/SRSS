## Descripción del reto
Try [here](http://titan.picoctf.net:52929/) to find the flag

## Solución
- Primero nos muestra la pagina en la cual ingresamos nuestros datos y al darle al boton, nos muestra una pagina en donde sale que tenemos que agreagr un numero OTP.
![[Pasted image 20251004120900.png]]
![[Pasted image 20251004120936.png]]

- Como ingresar cualquier valor da error, vamos a abrir el BurpSuite, para ver los envíos y métodos, una vez abierto volvemos a hacer el formulario de la pagina y enviar el numero OTP, ahora nos enfocamos en el método POST y URL `/dashboard`.
![[Pasted image 20251004122238.png]]

-  Los mandamos al `Repeater` (tanto el Request como el Response) y quitamos el numero OTP y lo enviamos de nuevo, eso nos dará la bandera.
![[Pasted image 20251004122630.png]]
![[Pasted image 20251004122658.png]]

picoCTF{#0TP_Bypvss_SuCc3$S_c94b61ac}
## Notas


## Referencia
