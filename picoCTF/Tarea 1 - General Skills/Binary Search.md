## Descripción del reto
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/20/challenge.zip)

`ssh -p 56528 ctf-player@atlas.picoctf.net`Using the password `6abf4a82`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

## Solución

Descargamos el archivo y lo descomprimimos, nos metemos al servidor proporcionado y empezamos a jugar.
```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_atlas/20/challenge.zip
--2025-09-14 06:45:15--  https://artifacts.picoctf.net/c_atlas/20/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.72, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1041 (1.0K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                       100%[==================================================================>]   1.02K  --.-KB/s    in 0s      

2025-09-14 06:45:15 (358 MB/s) - 'challenge.zip' saved [1041/1041]

BLOODANGELIX-picoctf@webshell:~$ ls
challenge.zip
BLOODANGELIX-picoctf@webshell:~$ unzip challenge.zip 
Archive:  challenge.zip
   creating: home/ctf-player/drop-in/
  inflating: home/ctf-player/drop-in/guessing_game.sh  
BLOODANGELIX-picoctf@webshell:~$ ssh -p 56528 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:56528 ([18.217.83.136]:56528)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:56528' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 340
Higher! Try again.
Enter your guess: 500
Lower! Try again.
Enter your guess: 400
Higher! Try again.
Enter your guess: 450
Higher! Try again.
Enter your guess: 470
Lower! Try again.
Enter your guess: 466
Lower! Try again.
Enter your guess: 455
Higher! Try again.
Enter your guess: 458
Higher! Try again.
Enter your guess: 463
Lower! Try again.
Enter your guess: 459
Congratulations! You guessed the correct number: 459
Here's your flag: picoCTF{g00d_gu355_bee04a2a}
Connection to atlas.picoctf.net closed.
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{g00d_gu355_bee04a2a}
## Notas


## Referencia
