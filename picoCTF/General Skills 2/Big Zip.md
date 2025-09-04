## Descripción del reto
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
--2025-09-04 03:06:19--  https://artifacts.picoctf.net/c/504/big-zip-files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.72, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3182988 (3.0M) [application/octet-stream]
Saving to: 'big-zip-files.zip'

big-zip-files.zip                   100%[==================================================================>]   3.04M  1.82MB/s    in 1.7s    

2025-09-04 03:06:21 (1.82 MB/s) - 'big-zip-files.zip' saved [3182988/3182988]

BLOODANGELIX-picoctf@webshell:~$ ls
big-zip-files.zip

BLOODANGELIX-picoctf@webshell:~$ unzip big-zip-files.zip 

*Muchos archivos que no voy a poner*

BLOODANGELIX-picoctf@webshell:~$ ls
big-zip-files  big-zip-files.zip

BLOODANGELIX-picoctf@webshell:~$ file *
big-zip-files:     directory
big-zip-files.zip: Zip archive data, at least v1.0 to extract, compression method=store

BLOODANGELIX-picoctf@webshell:~$ grep -r picoCTF big-zip-files
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```

## Notas
wget : Descargar archivos desde una dirección o pagina web.

unzip "nombre del archivo comprimido" : Sirve para descomprimir.

file : Ver el tipo de archivo.

grep -r : buscar de forma recursiva en los archivos, dentro de los directorios y subdirectorios.

## Referencia
[Realice una búsqueda recursiva Grep en todos los archivos y directorios](https://es.linux-console.net/?p=19824)