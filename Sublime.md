# Sublime Text 3

1. Install Sublime Text 3:  
[Sublime Text 3](https://www.sublimetext.com/3)  
Instructions are pretty straight forward, install with the method you want.  

2. Install Sublime's Package Control plugin first:  
[Package Control](https://packagecontrol.io/installation)  
You should have Sublime Text 3. If you are like me and cannot open the console with the regular shortcut (because of your layout), click on the `show console` option under `View`.  

3. Install the required plugins:  
To install plugins, press `Ctrl+Shift+P` and enter `Package Control: Install Package`, select it by pressing enter and install the following:  
`TOML`, `Rust Enhanced`, `RustAutoComplete`

4. Configure RustAutoComplete:  
Go into the `Preferences` tab in the top menu, then into `Package Settings`, `RustAutoComplete`, `Settings - User`  
Paste this:  
```
{
        "racer": "racer",
                "search_paths": [
                        "/home/{USER}/.rustup/toolchains/{TOOLCHAIN}/lib/rustlib/src/rust/src"
                ]
}
```
Where {USER} is your user name and {TOOLCHAIN} is the toolchain you will use for completion. (this path should be the same as the `RUST_SRC_PATH` you have set with racer)

5. Everything works  
BUT, errors are checked on save only, not in real time.
