## Descripción
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz).

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p rust_fixme_3
aaron-tank_3@aaron-tankVirtualBox:~$ cd rust_fixme_3
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ wget https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz
--2026-10-01 12:39:49--  https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.66, 13.226.187.40, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.37]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1915 (1,9K) [application/octet-stream]
Guardando como: ‘fixme3.tar.gz’

fixme3.tar.gz       100%[===================>]   1,87K  --.-KB/s    en 0s      

2026-10-01 12:39:49 (23,3 MB/s) - ‘fixme3.tar.gz’ guardado [1915/1915]

aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ ls -lh
total 4.0K
-rw-rw-r-- 1 aaron-tank_3 aaron-tank_3 1.9K Sep 22 23:30 fixme3.tar.gz
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ file *
fixme3.tar.gz: gzip compressed data, was "fixme3.tar", last modified: Sun Aug 16 21:31:35 2026, max compression, original size modulo 2^32 20480
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ tar -xzf fixme3.tar.gz
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ find . -type f -name "*.rs"
./fixme3/src/main.rs
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ cat ./fixme3/src/main.rs
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
    
    // unsafe {
        // Decrypt the flag operations 
        let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);

        // Creating a pointer 
        let decrypted_ptr = decrypted_buffer.as_ptr();
        let decrypted_len = decrypted_buffer.len();
        
        // Unsafe operation: calling an unsafe function that dereferences a raw pointer
        let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);

        borrowed_string.push_str(&String::from_utf8_lossy(decrypted_slice));
    // }
    println!("{}", borrowed_string);
}

fn main() {
    // Encrypted flag values
    let hex_values = ["71", "35", "11", "73", "2f", "17", "53", "71", "12", "90", "7e", "53", "63", "e1", "01", "35", "7e", "59", "60", "f6", "03", "86", "7f", "56", "41", "29", "30", "6f", "08", "c3", "61", "f9", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: ");
    decrypt(encrypted_buffer, &mut party_foul);
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ nano ~/rust_fixme_3/fixme3/src/main.rss
el único cambio que le hice al código, era que la función unsafe estaba comentada con "//" solo quite las diagonales donde empieza la función y donde termina 

aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3$ cd ~/rust_fixme_3/fixme3
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_3/fixme3$ cargo run
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/aaron-tank_3/rust_fixme_3/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 10.91s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: academy{n0w_y0uv3_f1x3d_1h3m_411}



