# Rust IDEs

On this repository you will find simple tutorials describing you how to set-up your Rust progamming environment to be able to start with the right tools!

## Setting up Rust

Rust can be installed multiple different ways.
Using [Rustup](https://www.rustup.rs/) is the preferred way as it will be the same on every machine. (choose the default installation)

You then need to install rust's source code for racer to find its completion:
`rustup component add rust-src`

You will also need to install and configure racer:
(you might need to install `gcc` with your distribution's package management tool)
`cargo install racer`

Racer needs to be added to your path:
* On Linux:
In your `.profile` file, add those lines:
```sh
export PATH="$PATH:~/.cargo/bin" # This, or something similar should already be here
export RUST_SRC_PATH="$(rustc --print sysroot)/lib/rustlib/src/rust/src"
```

## Getting Started

1. [Visual Studio Code](VSCode.md)
2. Sublime Text 3
3. [Vim](Vim.md)
4. Atom
5. IntelliJ IDEA
