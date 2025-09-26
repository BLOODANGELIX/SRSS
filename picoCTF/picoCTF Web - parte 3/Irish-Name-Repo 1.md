## Descripción del reto
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## Solución
- Al principio muestra una pagina en la cual debemos acceder al menú e irnos a iniciar sesión con un username y password.
![[Pasted image 20250925195609.png]]

- En este login, debemos inspeccionar el código fuente para revisar como esta construida la pagina. Habilitamos el `input` escondido dentro del codigo y lo cambiamos a 1. Ahora nos dan una pista de como le podemos hacer para ingresar.
![[Pasted image 20250925200156.png]]

- Ahora en username ponemos, `admin ' or 1=1;`, con esto nos mostrara la bandera.
![[Pasted image 20250925200317.png]]

picoCTF{s0m3_SQL_fb3fe2ad}

## Notas


## Referencia