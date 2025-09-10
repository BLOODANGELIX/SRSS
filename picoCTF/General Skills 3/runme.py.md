## Descripción del reto
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

## Solución

Lo único a tenemos que usar wget para descargar el archivo y después ejecutarlo con python3
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2025-09-10 02:36:14--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.77, 3.170.131.18, 3.170.131.72, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.77|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                            100%[==================================================================>]     270  --.-KB/s    in 0.001s  

2025-09-10 02:36:14 (235 KB/s) - 'runme.py' saved [270/270]

BLOODANGELIX-picoctf@webshell:~$ python3 runme.py
picoCTF{run_s4n1ty_run}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{run_s4n1ty_run}
## Notas


## Referencia