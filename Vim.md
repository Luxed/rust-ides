# Vim Setup

## Linux (Ubuntu based dstributions)
0. install Rust RLS
Follow instructions here: [RLS](https://github.com/rust-lang-nursery/rls)
You shouldn't need to configure Racer as it has been done before.

1. Install Python 3: (or use the python version you already have)
`sudo apt install python3`

2. Install Vim 8:
Vim 8 is essential for async support! You can choose to use the slow Syntastic but it won't be as good of an experience.
Check the version of vim available on your distribution first. Here, for Ubuntu:
`sudo apt search ^vim$`
The version reported for me is 7.4. Let's install the correct repo for Vim8:
`sudo add-apt-repository ppa:jonathonf/vim`

Then to install:
```bash
sudo apt update
sudo apt install vim
```

3. Install the plugin manager of your choice
We will use [Vim-Plug](https://github.com/junegunn/vim-plug) for the vimrc example.
Use the instructions provided on the github page to install the plugin manager.

4. Create the correct vimrc file containing required 
(the rust toolchain location can be found with this command: `rustc --print sysroot`)
```vim
call plug#begin()

Plug 'valloric/youcompleteme'
Plug 'w0rp/ale'

call plug#end()

let g:ycm_rust_src_path="/home/luxed/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/src/rust/src"

let g:ale_linters = {'rust': ['rls']}
```

Execute the following commands in Vim: `:source %` and then `:PlugInstall`

5. Setting up youcompleteme for rust syntax
Go into the following directory: `~/.vim/plugged/youcompleteme`
And execute the following command: `./install.py --rust-completer` (you might need to install `CMake`, `g++` and `python-dev` for this to work)

6. You're done ! everything works ! (I hope)

## Known Issues
* Error 404 when updating apt on Ubuntu 16.10:
Simply force the xenial repo to be used. After adding the repo with `add-apt-repository`, you can edit the file found in `/etc/apt/sources.list.d/` that corresponds to the repo (it begins by `jonathonf`) and replace every occurence of `yakkety` (in this case) with `xenial`
