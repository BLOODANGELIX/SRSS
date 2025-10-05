## Descripción del reto
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:52253/).

## Solución
- Al principio muestra esta pagina.
![[Pasted image 20251004211210.png]]

- Después inspeccionamos el código fuente y nos vamos a `Sources`, en donde nos mostrara las carpetas del sitio, ingresamos a la URL, `/secrets/`, de ahi nos abrirá otra carpeta llamada `hidden`, e ingresamos en la URL `/secret/hidden/`, y asi con cada carpeta hasta llegar a `/secret/hidden/superhidden/`, en donde esta la bandera.
![[Pasted image 20251004212058.png]]
![[Pasted image 20251004212123.png]]
![[Pasted image 20251004212302.png]]

picoCTF{succ3ss_@h3n1c@10n_39849bcf}

## Notas


## Referencia
