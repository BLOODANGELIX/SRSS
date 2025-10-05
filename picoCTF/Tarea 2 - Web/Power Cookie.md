## Descripción del reto
Can you get the flag?Go to this [website](http://saturn.picoctf.net:57482/) and see what you can discover.

## Solución
- Al principio muestra una pagina con un boton, el cual al precionar nos manda a otra pagina vacía.
![[Pasted image 20251004203320.png]]
![[Pasted image 20251004203334.png]]

- Por lo tanto buscamos en las cookies, y vemos que hay una llamada `isAdmin`, la cual tiene valor de 0, cambias el valor a 1 y nos mostrara la bandera.
![[Pasted image 20251004203418.png]]
![[Pasted image 20251004203448.png]]

picoCTF{gr4d3_A_c00k13_65fd1e1a}
## Notas


## Referencia
