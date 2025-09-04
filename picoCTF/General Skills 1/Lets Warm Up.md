## Descripción del reto
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
## Solución
Utilice una pagina para convertir de hexadecimal a ASCII
## Notas
- Siempre hay que poner la solución entre llaves y no entre paréntesis.
- CyberChef es un sitio que permite codificar y decodificar en diferentes formatos.

picoCTF{p}

``` python
>>> int(0x70)
112
>>> chr(112)
'p'
>>> 
```
## Referencia
[CyberChef](https://michaeltri.github.io/CyberChef/?recipe=%5B%7B%22op%22%3A%22From%20Hex%22%2C%22args%22%3A%5B%22Space%22%5D%7D%5D&input=MHg3MA)