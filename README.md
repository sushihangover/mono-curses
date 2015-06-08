# Mono-Curses OS-X 64-bit 

Clone the repo and checkout the **osx-64bit** branch

    git clone https://github.com/sushihangover/mono-curses.git
    git check osx-64bit 

Set our path to your 64-bit version of Mono and set your Mono package config env var to that install

**Example:**

    export PATH=$HOME/mono-install/bin
    export PKG_CONFIG_PATH=/$HOME/mono-install/lib/pkgconfig
    #WARNING: by default it installs into /usr/local
    ./configure --prefix=/$HOME/mono-install
    make 
    make install

That should do it, lets do a check arch check:

    file libmono-curses.dylib 
    libmono-curses.dylib: Mach-O 64-bit dynamically linked shared library x86_64
    
    file mono-curses.dll
    mono-curses.dll: PE32+ executable for MS Windows (DLL) (console) Mono/.Net assembly

FYI: The difference in a [PE 32-bit and 64-bit](http://en.wikipedia.org/wiki/Portable_Executable) is show below:

    file mono-curses.dll
    mono-curses.dll: **PE32+** executable for MS Windows (DLL) (console) Mono/.Net assembly
    
    file mono-curses-32.dll 
    mono-curses-32.dll: **PE32 **executable for MS Windows (DLL) (console) **Intel 80386 32-bit **Mono/.Net assembly

There are a couple of tests that are built during the *make* you can run:

    (make test) mono test.exe (Unicode sample, any key to exit)
    (make gtest) mono gtest.exe (Ctrl-C to exit app)
    (make mltest) mono mltest.exe (Timer events do not work as expected(?), Ctrl-C to exit app)

