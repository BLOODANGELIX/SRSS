## Descripción del reto
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 7449`, but it doesn't speak English...
## Solución
- Primero se ingreso el comando nc con la dirección y puerto.
```
BLOODANGELIX-picoctf@webshell:~$ nc mercury.picoctf.net 7449
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
102 
50 
100 
55 
99 
97 
102 
97 
125 
10 
```

- Después lo pase por CyberChef para transformarlo de binario a texto.

picoCTF{g00d_k1tty!_n1c3_k1tty!_f2d7cafa}

## Notas
Se puede hacer de otra manera mas profesional por así decirlo, creando un archivo con todos los números y recorriendo el archivo para meterlos en un arreglo o lista, de ahí ir recorriendo el arreglo y transformando los números en texto plano.
## Referencia
[CyberChef](https://michaeltri.github.io/CyberChef/?recipe=%5B%7B%22op%22%3A%22From%20Hex%22%2C%22args%22%3A%5B%22Space%22%5D%7D%5D&input=MHg3MA)