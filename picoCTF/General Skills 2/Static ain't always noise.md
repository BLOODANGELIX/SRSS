## Descripción del reto
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static)? This [BASH script](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh) might help!
## Solución

#### Solucion 1
- Descargar los archivos (static y ltdis.sh) con wget
```
BLOODANGELIX-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
--2025-09-03 17:02:56--  https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                              100%[==================================================================>]   8.18K  --.-KB/s    in 0s      

2025-09-03 17:02:56 (78.8 MB/s) - 'static' saved [8376/8376]

BLOODANGELIX-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh
--2025-09-03 17:03:18--  https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                            100%[==================================================================>]     785  --.-KB/s    in 0s      

2025-09-03 17:03:18 (471 MB/s) - 'ltdis.sh' saved [785/785]
```

- Mostrar los archivos con ls. y luego utilizar el file * para mostrar los archivos y de que tipo son.
```
BLOODANGELIX-picoctf@webshell:~$ ls
README.txt  ltdis.sh  static
BLOODANGELIX-picoctf@webshell:~$ file *
README.txt: ASCII text, with escape sequences
ltdis.sh:   Bourne-Again shell script, ASCII text executable
static:     ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=17ad46e6c58b7c40148a89923e314662595d101b, not stripped

BLOODANGELIX-picoctf@webshell:~$ cat ltdis.sh 
#!/bin/bash


echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
```

- Utilizar el strings y un pipe para ejecutar el grep y encontrar la bandera
```
BLOODANGELIX-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_ccb2b43e}
BLOODANGELIX-picoctf@webshell:~$   
```


#### Solucion 2

```
BLOODANGELIX-picoctf@webshell:~$ bash ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset

BLOODANGELIX-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_ccb2b43e}
```

picoCTF{d15a5m_t34s3r_ccb2b43e}
## Notas

bash : Le dice al sistema que ejecute el archivo con el intérprete de Bash (aunque no sea ejecutable o no tenga la "shebang" `#!/bin/bash`).

## Referencia
