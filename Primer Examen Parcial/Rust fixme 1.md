## Descripción
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/b9cfc84c442958b8ac848ddc0692bed9ef01a15877b8d37f36afbe68b5849acc/fixme1.tar.gz).

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p rust_fixme_1
aaron-tank_3@aaron-tankVirtualBox:~$ cd rust_fixme_1
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ wget https://challenge-files.cylabacademy.net/library/b9cfc84c442958b8ac848ddc0692bed9ef01a15877b8d37f36afbe68b5849acc/fixme1.tar.gz
--2026-10-01 12:03:23--  https://challenge-files.cylabacademy.net/library/b9cfc84c442958b8ac848ddc0692bed9ef01a15877b8d37f36afbe68b5849acc/fixme1.tar.gz
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.37, 13.226.187.22, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.40]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1549 (1,5K) [application/octet-stream]
Guardando como: ‘fixme1.tar.gz’

fixme1.tar.gz       100%[===================>]   1,51K  --.-KB/s    en 0s      

2026-10-01 12:03:23 (7,93 MB/s) - ‘fixme1.tar.gz’ guardado [1549/1549]

aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ ls -lh
total 4.0K
-rw-rw-r-- 1 aaron-tank_3 aaron-tank_3 1.6K Sep 22 23:30 fixme1.tar.gz
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ file *
fixme1.tar.gz: gzip compressed data, was "fixme1.tar", last modified: Sun Aug 16 21:31:35 2026, max compression, original size modulo 2^32 20480
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ cat *.rs
cat: '*.rs': No such file or directory
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ tar -xzf fixme1.tar.gz
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ ls -lh
total 8.0K
drwxrwxr-x 3 aaron-tank_3 aaron-tank_3 4.0K Dec 16  2024 fixme1
-rw-rw-r-- 1 aaron-tank_3 aaron-tank_3 1.6K Sep 22 23:30 fixme1.tar.gz
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ find . -type f -name "*.rs"
./fixme1/src/main.rs
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ cat ./fixme1/src/main.rs
use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS") // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["71", "35", "11", "73", "2f", "17", "53", "71", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        ret; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        ":?", // How do we print out a variable in the println function? 
        String::from_utf8_lossy(&decrypted_buffer)
    );
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ nano ~/rust_fixme_1/fixme1/src/main.rss
Aquí hice algunas correciones al código 
let key = String::from("CSUCKS")  agrugue un " ; " 
let key = String::from("CSUCKS") ;
ret; complete la instrucción
return;
":?" lo cambie por "{}"
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1$ cd ~/rust_fixme_1/fixme1
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1/fixme1$ cargo run
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1/fixme1$ sudo apt update
sudo apt install cargo -y
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1/fixme1$ cd ~/rust_fixme_1/fixme1
aaron-tank_3@aaron-tankVirtualBox:~/rust_fixme_1/fixme1$ cargo run
    Updating crates.io index
  Downloaded rayon v1.10.0
  Downloaded either v1.13.0
  Downloaded xor_cryptor v1.2.3
  Downloaded rayon-core v1.12.1
  Downloaded crossbeam-utils v0.8.20
  Downloaded crossbeam-epoch v0.9.18
  Downloaded crossbeam-deque v0.8.5
  Downloaded 7 crates (379.2KiB) in 0.76s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/aaron-tank_3/rust_fixme_1/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 16.72s
     Running `target/debug/rust_proj`
academy{4r3_y0u_4_ru$t4c30n_n0w?}
## Notas Adicionales


## Referencias

