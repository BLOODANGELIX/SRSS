## Descripción del reto
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
--2025-10-07 23:26:05--  https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 65.9.121.109, 65.9.121.43, 65.9.121.24, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|65.9.121.109|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1415 (1.4K) [application/octet-stream]
Saving to: ‘fixme1.tar.gz’

fixme1.tar.gz                                   100%[====================================================================================================>]   1.38K  --.-KB/s    in 0s      

2025-10-07 23:26:06 (44.6 MB/s) - ‘fixme1.tar.gz’ saved [1415/1415]

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1]
└─$ tar -xf fixme1.tar.gz

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1]
└─$ ls
fixme1  fixme1.tar.gz

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1]
└─$ cd fixme1     
 
┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1/fixme1]
└─$ sudo apt install cargo -y      
[sudo] password for kali:

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1/fixme1]
└─$ ls                
Cargo.lock  Cargo.toml  src

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1/fixme1]
└─$ cd src   

┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_1/fixme1/src]
└─$ ls
main.rs

┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_1/fixme1/src]
└─$ open main.rs 

┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_1/fixme1/src]
└─$ cd ..

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1/fixme1]
└─$ cargo build
   Compiling rust_proj v0.1.0 (/home/kali/picoCTF/Parcial_1/Rust_fixme_1/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.62s

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_1/fixme1]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

```


picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

## Notas


## Referencia
