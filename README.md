# Mono-Curses OS-X 64-bit 


Clone the repo and checkout the osx-64bit branch

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

That should do it. There are a couple of tests that a built you can run:

    (make test) mono test.exe (Unicode sample, any key to exit)
    (make gtest) mono gtest.exe (Ctrl-C to exit app)
    (make mltest) mono mltest.exe (Timer events do not work as expected(?), Ctrl-C to exit app)

