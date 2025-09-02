## Descripción del reto
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.
## Solución
#### Solución 1
- Conectarse a la dirección con su puerto y después agregar un pipe para que ejecute en seguida el segundo comando 'grep'.
```
BLOODANGELIX-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 | grep picoCTF
picoCTF{digital_plumb3r_5ea1fbd7}
^C
BLOODANGELIX-picoctf@webshell:~$ 
```

#### Solución 2
- Conectarse a la dirección con su puerto y después guardarlo en un archivo llamado 'bandera', después salirse con Ctrl+c y utilizar el comando cat con el archivo bandera y utilizar una pipe para el segundo comando grep.
```
BLOODANGELIX-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 > bandera    
^C
BLOODANGELIX-picoctf@webshell:~$ cat bandera | grep picoCTF
picoCTF{digital_plumb3r_5ea1fbd7}
```

picoCTF{digital_plumb3r_5ea1fbd7}
## Notas
'comando' | 'comando' : se llama pipe y hace que después de ejecutar el primer comando se ejecute el segundo a la derecha de la pipe.
## Referencia
[All about pipes, by The Linux Information Project (LINFO)](https://www.linfo.org/pipes.html)
