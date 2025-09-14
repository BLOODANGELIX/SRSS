## Descripción del reto
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 63685`

## Solución

Entramos a la direccion y empezamos a jugar, para resolverlo tuve que utilizar libreta.
```
BLOODANGELIX-picoctf@webshell:~$ nc titan.picoctf.net 63685

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11011100
Binary Number 2: 00001000


Question 1/6:
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11100100
Correct!

Question 2/6:
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 10111000
Incorrect. Try again
Enter the binary result: 110111000
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00001000
Correct!

Question 4/6:
Operation 4: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11011100
Correct!

Question 5/6:
Operation 5: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11011100000
Correct!

Question 6/6:
Operation 6: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00000100
Correct!

Enter the results of the last operation in hexadecimal: 0x4

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_675602ae}
^Z
[13]+  Stopped                 nc titan.picoctf.net 63685
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_675602ae}
## Notas


## Referencia
