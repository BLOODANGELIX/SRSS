## Descripción del reto
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `abcba9f7`

Additional details will be available after launching your challenge instance.

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ ssh ctf-player@venus.picoctf.net -p 55339
The authenticity of host '[venus.picoctf.net]:55339 ([3.131.124.143]:55339)' can't be established.
ED25519 key fingerprint is SHA256:P1f6h95BrSVnJbm2AKhphfHHGEyAeThib/rN/AwKs24.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[venus.picoctf.net]:55339' (ED25519) to the list of known hosts.
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1103-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt

ctf-player@pico-chall$ file *
1of3.flag.txt:            ASCII text
instructions-to-2of3.txt: ASCII text

ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_

ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd /

ctf-player@pico-chall$ ls
2of3.flag.txt  boot  etc   instructions-to-3of3.txt  lib64  mnt  proc  run   srv  tmp  var
bin            dev   home  lib                       media  opt  root  sbin  sys  usr

ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_

ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~

ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
21cac893}
```

picoCTF{xxsh_0ut_0f_\/\/4t3r_21cac893}
## Notas
ssh "usuario o nombre de usuario"@"direccion" -p "puerto" : este comando sirve para conectarse de manera segura a una direccion con su usuario, direccion y puerto.

ls : Muestra la lista de los archivos y carpetas dentro de un directorio.

cat : Muestra el contenido de los archivos.

cd / : Sirve para moverse al directorio raiz.

cd ~ : Sirve para volver al directorio del usuario.
## Referencia
