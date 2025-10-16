## Descripción del reto
[🥛](http://mercury.picoctf.net:7585/)

## Solución

- Primero entramos ala pagina y vemos que es un GIF.
- Descargamos la imagen e instalamos la herramienta `zsteg`, para utilizarlo en la imagen. Eso nos dará la bandera.
```
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4]
└─$ wget http://mercury.picoctf.net:7585/concat_v.png                                                                                   
--2025-10-16 14:26:44--  http://mercury.picoctf.net:7585/concat_v.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:7585... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png                                    100%[====================================================================================================>]  17.26M  4.33MB/s    in 5.6s    

2025-10-16 14:26:50 (3.09 MB/s) - ‘concat_v.png’ saved [18095920/18095920]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4]
└─$ export RUBY_THREAD_VM_STACK_SIZE=500000000

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4]
└─$ sudo gem install zsteg
Fetching rainbow-3.1.1.gem
Fetching zsteg-0.2.13.gem
Fetching iostruct-0.5.0.gem
Fetching zpng-0.4.5.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.5
Successfully installed iostruct-0.5.0
Successfully installed zsteg-0.2.13
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.5
Installing ri documentation for zpng-0.4.5
Parsing documentation for iostruct-0.5.0
Installing ri documentation for iostruct-0.5.0
Parsing documentation for zsteg-0.2.13
Installing ri documentation for zsteg-0.2.13
Done installing documentation for rainbow, zpng, iostruct, zsteg after 1 seconds
4 gems installed

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-4]
└─$ zsteg concat_v.png                        
imagedata           .. text: "\n\n\n\n\n\n\t\t"
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
        from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
        from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
        from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
         ... 5208346 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'

```

picoCTF{imag3_m4n1pul4t10n_sl4p5}
## Notas


## Referencia
