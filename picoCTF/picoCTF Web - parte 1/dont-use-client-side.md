## Descripción del reto
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/29835/` ([link](https://jupiter.challenges.picoctf.org/problem/29835/)) or http://jupiter.challenges.picoctf.org:29835

## Solución
Nos muestra una pagina en la cual deberemos ingresar una contraseña correcta para que nos la valide que es correcta.
![[Pasted image 20250918200524.png]]

Entonces inspeccionamos la pagina web, y notamos que en el código esta una función que verifica la contraseña en la cual, esta la contraseña puesta de forma aleatoria para confundir, pero la resolución es ir acomodando el dicha contraseña según como es una cadena de caracteres.
![[Pasted image 20250918200736.png]]

Vamos a ir ordenándola en primer lugar y después la armamos completamente.
```
pico
CTF{
no_c
lien
ts_p
lz_7
723c
e}
```

picoCTF{no_clients_plz_7723ce}
## Notas


## Referencia
