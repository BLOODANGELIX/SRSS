## Descripción del reto
Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py) using [this password](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt) to get [the flag](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en)?

## Solución
- Descargamos los archivos y ejecutamos el archivo `.py` de la siguiente forma: `python ende.py -d flag.txt.en`.

```
BLOODANGELIX-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py
--2025-10-07 19:20:49--  https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: 'ende.py'

ende.py                             100%[==================================================================>]   1.30K  --.-KB/s    in 0s      

2025-10-07 19:20:49 (1007 MB/s) - 'ende.py' saved [1328/1328]

BLOODANGELIX-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt
--2025-10-07 19:21:01--  https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: 'pw.txt'

pw.txt                              100%[==================================================================>]      33  --.-KB/s    in 0s      

2025-10-07 19:21:01 (20.7 MB/s) - 'pw.txt' saved [33/33]

BLOODANGELIX-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en
--2025-10-07 19:21:13--  https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: 'flag.txt.en'

flag.txt.en                         100%[==================================================================>]     140  --.-KB/s    in 0s      

2025-10-07 19:21:13 (82.3 MB/s) - 'flag.txt.en' saved [140/140]

BLOODANGELIX-picoctf@webshell:~$ python ende.py -d flag.txt.en
Please enter the password:aa821c16aa821c16aa821c16aa821c16
picoCTF{4p0110_1n_7h3_h0us3_aa821c16}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{4p0110_1n_7h3_h0us3_aa821c16}
## Notas


## Referencia
