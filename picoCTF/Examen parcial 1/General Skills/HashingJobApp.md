## Descripción del reto
If you want to hash with the best, beat this test!`nc saturn.picoctf.net 60238`

## Solución
- Primero nos conectamos a la dirección y puerto, a lo cual nos pedirá que utilicemos una decodificador MD5 Hash, con el cual decodificaremos las palabras que nos de.
``` linux
BLOODANGELIX-picoctf@webshell:~$ nc saturn.picoctf.net 51921
Please md5 hash the text between quotes, excluding the quotes: 'Abraham Lincoln'
Answer: 
2f7cfa603df2a25fce27ad69cd4be673
2f7cfa603df2a25fce27ad69cd4be673
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'bad dogs'
Answer: 
60cc96ffdc458c98395d6e7b6878a6e9
60cc96ffdc458c98395d6e7b6878a6e9
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Microsoft'
Answer: 
140864078aeca1c7c35b4beb33c53c34
140864078aeca1c7c35b4beb33c53c34
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}

BLOODANGELIX-picoctf@webshell:~$ 
```

## Notas
[MD5 Hash Generator](https://www.md5hashgenerator.com/)

## Referencia
