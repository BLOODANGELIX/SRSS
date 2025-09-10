## Descripción del reto

Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `54016` to get the flag?You'll also need the password `84b12bae`. If asked, accept the fingerprint with `yes`.

## Solución

Solo nos conectamos de forma segura a una direccion, con el usuario y su puerto.
Para despues solo ingresar su contraseña, de esta manera teniendo la bandera.
```
BLOODANGELIX-picoctf@webshell:~$ ssh ctf-player@titan.picoctf.net -p 54016
The authenticity of host '[titan.picoctf.net]:54016 ([3.139.174.234]:54016)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:54016' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_07a987ac}
Connection to titan.picoctf.net closed.
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{s3cur3_c0nn3ct10n_07a987ac}
## Notas

## Referencia