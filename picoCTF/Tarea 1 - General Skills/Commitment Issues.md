## Descripción del reto
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/76/challenge.zip)

## Solución

- Descargar el archivo de la dirección, después los descomprimimos.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/76/challenge.zip
--2025-09-14 05:27:50--  https://artifacts.picoctf.net/c_titan/76/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.77, 3.170.131.33, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.77|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19201 (19K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                       100%[==================================================================>]  18.75K  --.-KB/s    in 0.001s  

2025-09-14 05:27:50 (13.1 MB/s) - 'challenge.zip' saved [19201/19201]

BLOODANGELIX-picoctf@webshell:~$ ls
README.txt  challenge.zip
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
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/d2/
 extracting: drop-in/.git/objects/d2/63841da2567e3e869d2b90e8e3bdd8838555b5  
   creating: drop-in/.git/objects/c0/
 extracting: drop-in/.git/objects/c0/cc0495794727db1682daa105367f28112796af  
   creating: drop-in/.git/objects/e7/
 extracting: drop-in/.git/objects/e7/20dc26a1a55405fbdf4d338d465335c439fb3e  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/a6/
 extracting: drop-in/.git/objects/a6/dca68e4310585eac3b5c9caf0f75967dfe972c  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     

```

- Iniciamos el git e ingresamos al directorio descomprimido. Al final nos ponemos en el branch donde se hicieron los commit y hacemos un *gti log* para ver el historial de commits, copiamos el ID donde se creo la bandera y con un *git checkout* nos colocamos en el archivo creado.
```
BLOODANGELIX-picoctf@webshell:~$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint:   git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint:   git branch -m <name>
Initialized empty Git repository in /home/BLOODANGELIX-picoctf/.git/
BLOODANGELIX-picoctf@webshell:~$ ls  
README.txt  challenge.zip  drop-in
BLOODANGELIX-picoctf@webshell:~$ cd drop-in/
BLOODANGELIX-picoctf@webshell:~/drop-in$ ls
message.txt
BLOODANGELIX-picoctf@webshell:~/drop-in$ cat message.txt 
TOP SECRET
BLOODANGELIX-picoctf@webshell:~/drop-in$ git branch

[2]+  Stopped                 git branch
BLOODANGELIX-picoctf@webshell:~/drop-in$ git checkout master
Already on 'master'
BLOODANGELIX-picoctf@webshell:~/drop-in$ git log
[3]+  Stopped                 git log
BLOODANGELIX-picoctf@webshell:~/drop-in$ git log

[4]+  Stopped                 git log
BLOODANGELIX-picoctf@webshell:~/drop-in$ git checkout e720dc26a1a55405fbdf4d338d465335c439fb3e
Note: switching to 'e720dc26a1a55405fbdf4d338d465335c439fb3e'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at e720dc2 create flag
BLOODANGELIX-picoctf@webshell:~/drop-in$ ls
message.txt
BLOODANGELIX-picoctf@webshell:~/drop-in$ cat message.txt 
picoCTF{s@n1t1z3_7246792d}
BLOODANGELIX-picoctf@webshell:~/drop-in$ 
```

## Notas
[The CTF Primer](https://primer.picoctf.org/#_git_version_control)

## Referencia
