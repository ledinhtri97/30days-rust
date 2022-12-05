###Installing rustup

```
$ curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh
```

###Updating and Uninstalling

```
$ rustup update
```

```
$ rustup self uninstall
```


###Hello, World

```
mkdir -p src/hello_world
cd src/hello_world
```

- add file `main.rs` with code:

```
fn main() {
    println!("Hello, world!");
}
```

```
rustc main.rs
./main
Hello, world!
```

###Cargo

```
$ cargo new src/hello_cargo
$ cd src/hello_cargo
```

```
$ ls
Cargo.toml src/
```

- cargo build: This command creates an executable file in target/debug/hello_cargo
```
$ cargo build
   Compiling hello_cargo v0.1.0 (/data/gits/30days-rust/chap01-getting-started/src/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.28s
```

- cargo check: This command quickly checks your code to make sure it compiles but doesn’t produce an executable
```
$ cargo check
   Checking hello_cargo v0.1.0 (/data/gits/30days-rust/chap01-getting-started/src/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.05s
```

- cargo run: 
```
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.00s
     Running `target/debug/hello_cargo`
Hello, world!
```