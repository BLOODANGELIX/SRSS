## Descripción del reto
How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 54593
Username: picoplayer 
Password: H9RmN0m18U
```

## Solución

- Entrar de forma segura al servidor, despues entrar al directorio base y de ahi meterse al directorio *etc* en donde se encuentra el archivo crontab al cual se le hace un *cat* para ver su contenido.
```
BLOODANGELIX-picoctf@webshell:~$ ssh picoplayer@saturn.picoctf.net -p 58564
The authenticity of host '[saturn.picoctf.net]:58564 ([13.59.203.175]:58564)' can't be established.
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:9: [hashed name]
    ~/.ssh/known_hosts:11: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:58564' (ED25519) to the list of known hosts.
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

picoplayer@challenge:~$ cd /
picoplayer@challenge:/$ ls
bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
picoplayer@challenge:/$ cd etc/
picoplayer@challenge:/etc$ ls
adduser.conf            cron.monthly    fstab        init.d         logrotate.d          networks       rc0.d        shadow     sysctl.conf
alternatives            cron.weekly     gai.conf     inputrc        lsb-release          nsswitch.conf  rc1.d        shadow-    sysctl.d
apt                     crontab         group        issue          machine-id           opt            rc2.d        shells     systemd
bash.bashrc             dbus-1          group-       issue.net      magic                os-release     rc3.d        skel       terminfo
bindresvport.blacklist  debconf.conf    gshadow      kernel         magic.mime           pam.conf       rc4.d        ssh        timezone
binfmt.d                debian_version  gshadow-     ld.so.cache    mailcap              pam.d          rc5.d        ssl        tmpfiles.d
ca-certificates         default         gss          ld.so.conf     mailcap.order        passwd         rc6.d        subgid     ucf.conf
ca-certificates.conf    deluser.conf    host.conf    ld.so.conf.d   mime.types           passwd-        rcS.d        subgid-    ufw
cloud                   dhcp            hostname     legal          mke2fs.conf          profile        resolv.conf  subuid     update-motd.d
cron.d                  dpkg            hosts        libaudit.conf  modules-load.d       profile.d      rmt          subuid-    wgetrc
cron.daily              e2scrub.conf    hosts.allow  localtime      mtab                 python3        security     sudoers    xattr.conf
cron.hourly             environment     hosts.deny   login.defs     networkd-dispatcher  python3.8      selinux      sudoers.d  xdg
picoplayer@challenge:/etc$ cat crontrab
cat: crontrab: No such file or directory
picoplayer@challenge:/etc$ cat crontab 
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_d83baed1}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{Sch3DUL7NG_T45K3_L1NUX_d83baed1}
## Notas


## Referencia
