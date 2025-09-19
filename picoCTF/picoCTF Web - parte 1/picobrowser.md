## Descripción del reto
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921

## Solución
Empezamos con una sencilla pagina, en la cual al hacer click en el boton, nos muestra que no ingresamos en ella con el navegador `picobrowser`.
![[Pasted image 20250918201113.png]]

Entonces utilizamos el siguiente comando para simular que estamos usando `picobrowser` y que la pagina nos deje ver la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser" | grep picoCTF
```

![[Pasted image 20250918201554.png]]

picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}
## Notas


## Referencia
