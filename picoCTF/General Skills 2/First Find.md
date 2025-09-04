## Descripción del reto
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/501/files.zip)

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/501/files.zip
--2025-09-04 03:13:27--  https://artifacts.picoctf.net/c/501/files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3995553 (3.8M) [application/octet-stream]
Saving to: 'files.zip'

files.zip                           100%[==================================================================>]   3.81M  1.82MB/s    in 2.1s    

2025-09-04 03:13:29 (1.82 MB/s) - 'files.zip' saved [3995553/3995553]

BLOODANGELIX-picoctf@webshell:~$ ls
files.zip
BLOODANGELIX-picoctf@webshell:~$ unzip files.zip 
Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
  inflating: files/satisfactory_books/more_books/37121.txt.utf-8  
  inflating: files/satisfactory_books/23765.txt.utf-8  
  inflating: files/satisfactory_books/16021.txt.utf-8  
  inflating: files/13771.txt.utf-8   
   creating: files/adequate_books/
   creating: files/adequate_books/more_books/
   creating: files/adequate_books/more_books/.secret/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
  inflating: files/adequate_books/more_books/1023.txt.utf-8  
  inflating: files/adequate_books/46804-0.txt  
  inflating: files/adequate_books/44578.txt.utf-8  
   creating: files/acceptable_books/
   creating: files/acceptable_books/more_books/
  inflating: files/acceptable_books/more_books/40723.txt.utf-8  
  inflating: files/acceptable_books/17880.txt.utf-8  
  inflating: files/acceptable_books/17879.txt.utf-8  
  inflating: files/14789.txt.utf-8
  
BLOODANGELIX-picoctf@webshell:~$ file *
files:     directory
files.zip: Zip archive data, at least v1.0 to extract, compression method=store

BLOODANGELIX-picoctf@webshell:~$ grep -r picoCTF files
files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt:picoCTF{f1nd_15_f457_ab443fd1}
```

## Notas
wget : Descargar archivos desde una dirección o pagina web.

unzip "nombre del archivo comprimido" : Sirve para descomprimir.

file : Ver el tipo de archivo.

grep -r : buscar de forma recursiva en los archivos, dentro de los directorios y subdirectorios.

## Referencia
