## Descripción
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz).

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p rust_fixme_2 
aaron-tank_3@aaron-tankVirtualBox:~$ cd rust_fixme_2
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ wget https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz
--2026-10-01 12:23:14--  https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.37, 13.226.187.66, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.22]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1720 (1,7K) [application/octet-stream]
Guardando como: ‘fixme2.tar.gz’

fixme2.tar.gz       100%[===================>]   1,68K  --.-KB/s    en 0s      

2026-10-01 12:23:15 (13,1 MB/s) - ‘fixme2.tar.gz’ guardado [1720/1720]

aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ ls -lh
total 4.0K
-rw-rw-r-- 1 aaron-tank_3 aaron-tank_3 1.7K Sep 22 23:43 fixme2.tar.gz
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ file *
fixme2.tar.gz: gzip compressed data, was "fixme2.tar", last modified: Sun Aug 16 21:31:35 2026, max compression, original size modulo 2^32 20480
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ tar -xzf fixme2.tar.gz
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ find . -type f -name "*.rs"
./fixme2/src/main.rs
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ cat ./fixme2/src/main.rs
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &String){ // How do we pass values to a function that we want to change?

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
    let hex_values = ["71", "35", "11", "73", "2f", "17", "53", "71", "01", "1c", "7e", "59", "63", "e1", "61", "25", "0d", "c4", "60", "f2", "12", "a0", "18", "03", "51", "03", "36", "05", "0e", "f9", "42", "5b"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ nano ~/rust_fixme_2/fixme2/src/main.rss

hice estos cambios al codigo 
fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &String){   esta línea la cambie por "fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){"

let party_foul = String::from("Using memory unsafe languages is a: "); esta línea la cambie por "let mut party_foul = String::from("Using memory unsafe languages is a: ");"

decrypt(encrypted_buffer, &party_foul); esta línea la cambie por "decrypt(encrypted_buffer, &mut party_foul);"

aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2$ cd ~/rust_fixme_2/fixme2
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2/fixme2$ cargo run
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/aaron-tank_3/rust_fixme_2/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 10.04s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: academy{4r3_y0u_h4v1n5_fun_y31?}
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_2/fixme2$ 


