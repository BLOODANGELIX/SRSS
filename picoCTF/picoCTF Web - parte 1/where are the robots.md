## Descripción del reto
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/56830/` ([link](https://jupiter.challenges.picoctf.org/problem/56830/)) or http://jupiter.challenges.picoctf.org:56830

## Solución
Entramos al link proporciona y nos muestra una pagina vacia, entonces lo que tratamos es inspeccionar el codigo fuente.

Ya que no encontramos nada, intentamos buscar el archivo robots.txt, asi que lo ponemos en el link proporcionado:

``` html
https://jupiter.challenges.picoctf.org/problem/56830/robots.txt
```

Después nos manda a al archivo:
![[Pasted image 20250917105320.png]]

Ingresamos en `/1bb4c.html` dentro del link:
``` html
https://jupiter.challenges.picoctf.org/problem/56830/1bb4c.html
```

Ahí nos dara la bandera:
![[Pasted image 20250917105902.png]]

picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}
## Notas


## Referencia
