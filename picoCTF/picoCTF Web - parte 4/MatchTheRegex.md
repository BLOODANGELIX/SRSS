## Descripción del reto
How about trying to match a regular expression. The website is running [here](http://saturn.picoctf.net:57251/).

## Solución
- Al principio nos arroja a este sitio web, en el cual al meter cualquier cosa nos da error.
![[Pasted image 20250930212119.png]]
![[Pasted image 20250930212144.png]]

- Después revisamos el código fuente, para identificar donde se encuentra la expresión regular como lo indica el problema.
![[Pasted image 20250930212313.png]]

- Una vez encontrada, procedemos a pasar esa expresion a una pagina ([RegExr: Learn, Build, & Test RegEx](https://regexr.com/)) en la cual nos indicara como proseguir para hacer "Match" con la expresion.
![[Pasted image 20250930212459.png]]

- Una vez encontrada la similitud, ahora el resultado en texto, lo ingresamos en la pagina del reto y al darle `submit`, nos otorgara la bandera.
![[Pasted image 20250930212700.png]]

picoCTF{succ3ssfully_matchtheregex_0694f25b}

## Notas


## Referencia