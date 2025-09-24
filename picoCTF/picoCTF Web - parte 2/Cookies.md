## Descripción del reto
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:54219/](http://mercury.picoctf.net:54219/)

## Solución
- Al principio notamos que nos pide ingresar una galleta, la cual ya nos da una pista de lo que tenemos que escribir, para posteriormente darnos cuenta de que nos suelta otra pagina, pero ninguna bandera, a lo que tenemos que revisar con la extensión `CookieEditor`.
![[Pasted image 20250923203659.png]]

- Revisando vemos que tiene `name` con un valor, a lo cual si cambiamos el valor, cambia la pantalla, pero ese trabajo de ir probando cada numero es incomodo, por lo que nos vamos a la consola y escribimos el siguiente comando, para que ingrese de forma recursiva al servidor y cambie de valor a `name`, hasta dar con el valor correcto.
```
for i in {0..20}; do curl -s  http://mercury.picoctf.net:54219/check -H "Cookie: name=$i"; done | grep picoCTF
```
![[Pasted image 20250923204055.png]]

picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}
## Notas


## Referencia