## Descripción del reto
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/66/challenge.zip)

## Solución

- Descargar el archivo y descomprimirlo, ingresar al directorio que se descomprimió y aplicar un log, para ver el historial de commits, ahí nos aparecerá la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/66/challenge.zip
--2025-09-14 05:53:30--  https://artifacts.picoctf.net/c_titan/66/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.18, 3.170.131.72, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17740 (17K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                       100%[==================================================================>]  17.32K  --.-KB/s    in 0.005s  

2025-09-14 05:53:30 (3.50 MB/s) - 'challenge.zip' saved [17740/17740]

BLOODANGELIX-picoctf@webshell:~$ ls
challenge.zip
BLOODANGELIX-picoctf@webshell:~$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/33/
 extracting: drop-in/.git/objects/33/39c144a0c78dc2fbd3403d2fb37d3830be5d94  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
BLOODANGELIX-picoctf@webshell:~$ ls
challenge.zip  drop-in
BLOODANGELIX-picoctf@webshell:~$ cd drop-in 
BLOODANGELIX-picoctf@webshell:~/drop-in$ ls
message.txt
BLOODANGELIX-picoctf@webshell:~/drop-in$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...BLOODANGELIX-picoctf@webshell:~/drop-in$ git log

picoCTF{t1m3m@ch1n3_d3161c0f}

[5]+  Stopped                 git log
BLOODANGELIX-picoctf@webshell:~/drop-in$ 
```

picoCTF{t1m3m@ch1n3_d3161c0f}
## Notas


## Referencia
