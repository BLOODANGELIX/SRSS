## Descripción del reto
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/178/challenge.zip)

## Solución

Descargas el .zip, los descomprimimos, ingresamos al directorio descomprimido, y vemos las branches que hay, como hay tres, nos metemos en cada una y corremos el código para sacar las partes de las llaves.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/178/challenge.zip
--2025-09-14 06:23:24--  https://artifacts.picoctf.net/c_titan/178/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24640 (24K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                       100%[==================================================================>]  24.06K  --.-KB/s    in 0.004s  

2025-09-14 06:23:24 (5.51 MB/s) - 'challenge.zip' saved [24640/24640]

BLOODANGELIX-picoctf@webshell:~$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
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
 extracting: drop-in/.git/refs/heads/main  
   creating: drop-in/.git/refs/heads/feature/
 extracting: drop-in/.git/refs/heads/feature/part-1  
 extracting: drop-in/.git/refs/heads/feature/part-2  
 extracting: drop-in/.git/refs/heads/feature/part-3  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/77/
 extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690  
   creating: drop-in/.git/objects/b9/
 extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a  
   creating: drop-in/.git/objects/22/
 extracting: drop-in/.git/objects/22/58a0f267d57e8b6025e2a020b77fac7a553c92  
   creating: drop-in/.git/objects/6e/
 extracting: drop-in/.git/objects/6e/17fb3a35364b4f9bb8bef8b5e6a5af2d3e7dfa  
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/e44dd37ba0c0adc3d78d0b85d699859ec8d75c  
   creating: drop-in/.git/objects/8e/
 extracting: drop-in/.git/objects/8e/ea0627726fc363246015cb4c7e927e70286e87  
   creating: drop-in/.git/objects/7a/
 extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833  
   creating: drop-in/.git/objects/d1/
 extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258  
   creating: drop-in/.git/objects/05/
 extracting: drop-in/.git/objects/05/db9e274ff691e0f9fb492403b570629eb80aa9  
   creating: drop-in/.git/objects/4f/
 extracting: drop-in/.git/objects/4f/136da027f9a97032d53dd5f667dd6c7852737c  
   creating: drop-in/.git/objects/dd/
 extracting: drop-in/.git/objects/dd/f6fd2129098bf677ac010259a2a642060aea47  
   creating: drop-in/.git/objects/65/
 extracting: drop-in/.git/objects/65/5c7bfebe9c221369ab00ac7374d0d4bd4d62a9  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/main  
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1  
  inflating: drop-in/.git/logs/refs/heads/feature/part-2  
  inflating: drop-in/.git/logs/refs/heads/feature/part-3  
  inflating: drop-in/flag.py         
BLOODANGELIX-picoctf@webshell:~$ ls
challenge.zip  drop-in
BLOODANGELIX-picoctf@webshell:~$ cd drop-in/
BLOODANGELIX-picoctf@webshell:~/drop-in$ ls
flag.py
BLOODANGELIX-picoctf@webshell:~/drop-in$ python3 flag.py 
Printing the flag...
BLOODANGELIX-picoctf@webshell:~/drop-in$ git merge master
merge: master - not something we can merge
BLOODANGELIX-picoctf@webshell:~/drop-in$ git branch

[10]+  Stopped                 git branch
BLOODANGELIX-picoctf@webshell:~/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
BLOODANGELIX-picoctf@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')BLOODANGELIX-picoctf@webshell:~/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
BLOODANGELIX-picoctf@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')BLOODANGELIX-picoctf@webshell:~/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
BLOODANGELIX-picoctf@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")

print("w0rk_6c06cec1}")
```

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}
## Notas


## Referencia
