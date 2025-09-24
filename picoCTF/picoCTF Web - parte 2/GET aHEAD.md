## Descripción del reto
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:53554/](http://mercury.picoctf.net:53554/)

## Solución

- Al principio nos muestra una pantalla:
![[Pasted image 20250923200003.png]]

- Procedemos a inspeccionar la pagina y nos damos cuenta que dentro del codigo, la opcion roja tiene el metodo GET y la azul tiene el metodo POST, los cuales se pueden ver en la pestaña `NETWORK`.
![[Pasted image 20250923200356.png]]

- Ya una vez en `NETWORK`, seleccionamos el metodo POST, y nos mostrara una pequeña ventana en la cual escogeremos la opcion `Resend` con la cual reenviaremos solicitudes.
![[Pasted image 20250923200830.png]]

- Aquí en la opción POST a HEAD y reenviaremos la solicitud, eso nos dará la bandera.
![[Pasted image 20250923201037.png]]

picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}
## Notas


## Referencia