## Descripción del reto
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_3]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
--2025-10-07 23:55:31--  https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 65.9.121.119, 65.9.121.43, 65.9.121.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|65.9.121.119|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1776 (1.7K) [application/octet-stream]
Saving to: ‘fixme3.tar.gz’

fixme3.tar.gz                                   100%[====================================================================================================>]   1.73K  --.-KB/s    in 0.003s  

2025-10-07 23:55:32 (592 KB/s) - ‘fixme3.tar.gz’ saved [1776/1776]

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_3]
└─$ tar -xf fixme3.tar.gz

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_3]
└─$ ls
fixme3  fixme3.tar.gz

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_3]
└─$ cd fixme3/src  

┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_3/fixme3/src]
└─$ ls
main.rs

┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_3/fixme3/src]
└─$ open main.rs 
```

- Código corregido.
```RUST
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &mut String) {
    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decryption object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return;
    }
    let xrc = res.unwrap();

    // Did you know you have to do "unsafe operations in Rust?
    // https://doc.rust-lang.org/book/ch19-01-unsafe-rust.html
    // Even though we have these memory safe languages, sometimes we need to do things outside of the rules
    // This is where unsafe rust comes in, something that is important to know about in order to keep things in perspective
    
    unsafe {
        // Decrypt the flag operations 
        let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);

        // Creating a pointer 
        let decrypted_ptr = decrypted_buffer.as_ptr();
        let decrypted_len = decrypted_buffer.len();
        
        // Unsafe operation: calling an unsafe function that dereferences a raw pointer
        let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);

        borrowed_string.push_str(&String::from_utf8_lossy(decrypted_slice));
    }
    println!("{}", borrowed_string);
}

fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "12", "90", "7e", "53", "63", "e1", "01", "35", "7e", "59", "60", "f6", "03", "86", "7f", "56", "41", "29", "30", "6f", "08", "c3", "61", "f9", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: ");
    decrypt(encrypted_buffer, &mut party_foul);
}
```

```
┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_3/fixme3/src]
└─$ cd ..        

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_3/fixme3]
└─$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/picoCTF/Parcial_1/Rust_fixme_3/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 10.58s

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_3/fixme3]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

```

picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

## Notas


## Referencia