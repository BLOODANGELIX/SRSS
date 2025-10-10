## Descripción del reto
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
--2025-10-07 23:42:45--  https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 65.9.121.24, 65.9.121.43, 65.9.121.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|65.9.121.24|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1585 (1.5K) [application/octet-stream]
Saving to: ‘fixme2.tar.gz’

fixme2.tar.gz                                   100%[====================================================================================================>]   1.55K  --.-KB/s    in 0s      

2025-10-07 23:42:46 (122 MB/s) - ‘fixme2.tar.gz’ saved [1585/1585]

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2]
└─$ tar -xf fixme2.tar.gz 

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2]
└─$ ls
fixme2  fixme2.tar.gz

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2]
└─$ cd fixme2      

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2/fixme2]
└─$ ls
Cargo.lock  Cargo.toml  src

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2/fixme2]
└─$ cd src
               
┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_2/fixme2/src]
└─$ ls
main.rs

┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_2/fixme2/src]
└─$ open main.rs 

```

- Código corregido.
```RUST
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?

    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
    println!("{}", borrowed_string);
}


fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "0d", "c4", "60", "f2", "12", "a0", "18", "03", "51", "03", "36", "05", "0e", "f9", "42", "5b"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
}
```

```

┌──(kali㉿kali)-[~/…/Parcial_1/Rust_fixme_2/fixme2/src]
└─$ cd ..      

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2/fixme2]
└─$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/picoCTF/Parcial_1/Rust_fixme_2/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 9.38s

┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Rust_fixme_2/fixme2]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}

```

picoCTF{4r3_y0u_h4v1n5_fun_y31?}
## Notas


## Referencia
