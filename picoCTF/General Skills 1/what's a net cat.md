## Descripción del reto
Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `25103` to get the flag?
## Solución

```
BLOODANGELIX-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 25103
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_d0c64587}

BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{nEtCat_Mast3ry_d0c64587}
## Notas
nc 'direccion' 'puerto': permite conectarte a una direccion a travez de un puerto.

## Referencia
[nc(1): arbitrary TCP/UDP connections/listens - Linux man page](https://linux.die.net/man/1/nc)

