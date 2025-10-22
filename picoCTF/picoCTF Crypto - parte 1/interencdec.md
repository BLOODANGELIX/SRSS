## Descripción del reto
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/1/enc_flag).

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/1/enc_flag
--2025-10-22 01:28:08--  https://artifacts.picoctf.net/c_titan/1/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.77, 3.170.131.33, 3.170.131.72, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.77|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag              100%[=======================>]      73  --.-KB/s    in 0s      

2025-10-22 01:28:08 (84.2 MB/s) - 'enc_flag' saved [73/73]

BLOODANGELIX-picoctf@webshell:~$ cat enc_flag 
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyeG9OakJzTURCcGZRPT0nCg==
BLOODANGELIX-picoctf@webshell:~$ cat enc_flag | base64 -d
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ=='
BLOODANGELIX-picoctf@webshell:~$ echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ==" | base64 -d
wpjvJAM{jhlzhy_k3jy9wa3k_lh60l00i}
```

- Se pasa por un decodificador caesar y obtenemos la bandera.
![[Pasted image 20251021193233.png]]

picoCTF{caesar_d3cr9pt3d_ea60e00b}

## Notas


## Referencia