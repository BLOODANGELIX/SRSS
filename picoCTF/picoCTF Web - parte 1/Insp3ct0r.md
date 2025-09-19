## Descripción del reto
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/44924/` ([link](https://jupiter.challenges.picoctf.org/problem/44924/)) or http://jupiter.challenges.picoctf.org:44924

## Solución

Empezamos inspeccionando el código fuente del link proporcionado, después inspeccionamos el código fuente, de ahí vemos el HTML, en donde encontramos la primera parte de la bandera:
![[Pasted image 20250917103505.png]]

De ahi nos vamos al CSS, en donde esta la segunda parte:
![[Pasted image 20250917103757.png]]

La ultima parte esta en el JavaScript:
![[Pasted image 20250917103854.png]]

Todos estos links se encuentran dentro del HTML:
![[Pasted image 20250917103947.png]]

picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?f10be399}
## Notas


## Referencia

