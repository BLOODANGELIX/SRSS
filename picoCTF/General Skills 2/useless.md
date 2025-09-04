## Descripción del reto
There's an interesting script in the user's home directoryThe work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.

```
Hostname: saturn.picoctf.net
Port:     53708
Username: picoplayer
Password: password
```
## Solución
- Nos conectamos de forma segura a la direccion.
```
BLOODANGELIX-picoctf@webshell:~$ ssh picoplayer@saturn.picoctf.net -p 53708
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 6.8.0-1035-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
Last login: Wed Sep  3 17:19:51 2025 from 3.140.102.47
```

- Mostramos los archivos y directorios que hay.
```
picoplayer@challenge:~$ ls 
useless

picoplayer@challenge:~$ ls -la useless
-rwxr-xr-x 1 root root 517 Mar 16  2023 useless

picoplayer@challenge:~$ cat useless
#!/bin/bash
# Basic mathematical operations via command-line arguments

if [ $# != 3 ]
then
  echo "Read the code first"
else
        if [[ "$1" == "add" ]]
        then 
          sum=$(( $2 + $3 ))
          echo "The Sum is: $sum"  

        elif [[ "$1" == "sub" ]]
        then 
          sub=$(( $2 - $3 ))
          echo "The Substract is: $sub" 

        elif [[ "$1" == "div" ]]
        then 
          div=$(( $2 / $3 ))
          echo "The quotient is: $div" 

        elif [[ "$1" == "mul" ]]
        then
          mul=$(( $2 * $3 ))
          echo "The product is: $mul" 

        else
          echo "Read the manual"
         
        fi
fi
```

- Ejecutamos el archivo, después lo probamos y al final revisamos el manual.
```
picoplayer@challenge:~$ ./useless
Read the code first
picoplayer@challenge:~$ ./useless add 10 10
The Sum is: 20
picoplayer@challenge:~$ man useless        

useless
     useless, -- This is a simple calculator script

SYNOPSIS
     useless, [add sub mul div] number1 number2

DESCRIPTION
     Use the useless, macro to make simple calulations like addition,subtraction, multiplication and division.

Examples
     ./useless add 1 2
       This will add 1 and 2 and return 3

     ./useless mul 2 3
       This will return 6 as a product of 2 and 3

     ./useless div 6 3
       This will return 2 as a quotient of 6 and 3

     ./useless sub 6 5
       This will return 1 as a remainder of substraction of 5 from 6

Authors
     This script was designed and developed by Cylab Africa

     picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_4151}

picoplayer@challenge:~$ 
```

picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_4151}
## Notas
ls -la "nombre del archivo" :Muestra la lista de archivos con formato largo `-l` (permisos, dueño, grupo, tamaño, fecha, nombre) e incluye los archivos ocultos en la misma carpeta `-a`.

## Referencia
