## Descripción del reto
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.
`ssh -p 62153 ctf-player@saturn.picoctf.net`. 
The password is `af86add3`

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ ssh -p 62153 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:62153 ([13.59.203.175]:62153)' can't be established.
ED25519 key fingerprint is SHA256:lMXKIC17ONzyUJx7ZYBY5VSwoxCz20uq5/Nm+IhXKew.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:62153' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Specialer$ ls
-bash: ls: command not found
Specialer$ cd
Specialer$ ./
abra/ ala/  sim/  
Specialer$ ./
abra/ ala/  sim/  
Specialer$ for file in *
> do
>   if [ -d "$file" ]; then
>     echo "$file is a directory."
>   elif [ -f "$file" ]; then
>     echo "$file is a file."
>   fi
> done
abra is a directory.
ala is a directory.
sim is a directory.
Specialer$ cd abra/
Specialer$ for file in *
> do
>   if [ -d "$file" ]; then
>     echo "$file is a directory."
>   elif [ -f "$file" ]; then
>     echo "$file is a file."
>   fi
> done
cadabra.txt is a file.
cadaniel.txt is a file.
Specialer$ cd ../ala
Specialer$ for file in *
> do
>   if [ -d "$file" ]; then
>     echo "$file is a directory."
>   elif [ -f "$file" ]; then
>     echo "$file is a file."
>   fi
> done
kazam.txt is a file.
mode.txt is a file.
Specialer$ cd ../
Specialer$ cd ../ctf-player/
.hushlogin  .profile    abra/       ala/        sim/        
Specialer$ cd ../sim        
-bash: cd: ../sim: No such file or directory
Specialer$ cd ../ctf-player/sim/
Specialer$ for file in *
> do
>   if [ -d "$file" ]; then
>     echo "$file is a directory."
>   elif [ -f "$file" ]; then
>     echo "$file is a file."
>   fi
> done
city.txt is a file.
salabim.txt is a file.
Specialer$ for folder in abra ala sim
> do
>   cd "$folder"
>   for file in *
>   do
>     if [ -d "$file" ]; then
>       echo "$file: directory."
>     elif [ -f "$file" ]; then
>       echo "$folder/$file:"
>       printf "%s " $(<$file) # input redirection; alternative to 'cat'
>       printf "\n\n"
>     fi
>   done
>   cd ..
> done
-bash: cd: abra: No such file or directory
abra/city.txt:
05ed181c-4aa0-4d4a-8505-2fe6ca9097d3 

abra/salabim.txt:
#He was so kind, such a gentleman tied to the oceanside# 

ala/kazam.txt:
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_a8567b6f} 

ala/mode.txt:
Yummy! Ice cream! 

sim/city.txt:
05ed181c-4aa0-4d4a-8505-2fe6ca9097d3 

sim/salabim.txt:
#He was so kind, such a gentleman tied to the oceanside# 

Specialer$ 
```

picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_a8567b6f}

## Notas


## Referencia
