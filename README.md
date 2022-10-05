# rust101
First steps with rust

https://www.rust-lang.org/learn/get-started

brew install rust
mkdir ~/rust
cd ~/rust
cargo new hello-rust

   Created binary (application) `hello-rust` package

cd hello-rust
ls

   Compiling hello-rust v0.1.0 (/Users/emilzegers/rust/hello-rust)
    Finished dev [unoptimized + debuginfo] target(s) in 8.12s
     Running `target/debug/hello-rust`
Hello, world!

vi Cargo.toml

Add:
[dependencies]
ferris-says = "0.2"

cargo build

    Updating crates.io index
  Downloaded smawk v0.3.1
  Downloaded unicode-width v0.1.10
  Downloaded textwrap v0.13.4
  Downloaded smallvec v0.4.5
  Downloaded ferris-says v0.2.1
  Downloaded 5 crates (99.9 KB) in 0.64s
   Compiling unicode-width v0.1.10
   Compiling smawk v0.3.1
   Compiling smallvec v0.4.5
   Compiling textwrap v0.13.4
   Compiling ferris-says v0.2.1
   Compiling hello-rust v0.1.0 (/Users/emilzegers/rust/hello-rust)
    Finished dev [unoptimized + debuginfo] target(s) in 1m 12s

cd src

mv main.rs hello.rs
vi main.rs

use ferris_says::say; // from the previous step
use std::io::{stdout, BufWriter};

fn main() {
    let stdout = stdout();
    let message = String::from("Hello fellow Rustaceans!");
    let width = message.chars().count();

    let mut writer = BufWriter::new(stdout.lock());
    say(message.as_bytes(), width, &mut writer).unwrap();
}

cargo run
   Compiling hello-rust v0.1.0 (/Users/emilzegers/rust/hello-rust)
    Finished dev [unoptimized + debuginfo] target(s) in 2.16s
     Running `/Users/emilzegers/rust/hello-rust/target/debug/hello-rust`
 __________________________
< Hello fellow Rustaceans! >
 --------------------------
        \
         \
            _~^~^~_
        \) /  o o  \ (/
          '_   -   _'
          / '-----' \

https://stevedonovan.github.io/rust-gentle-intro/

TODO