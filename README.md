
# TikZiT

TikZiT is a graphical tool for rapidly creating graphs and string diagrams using PGF/TikZ. It was used, for example, to make all of the 2500+ diagrams in <a href="http://cambridge.org/pqp">this book</a>. This is forked from official repo to build a arm64 version on MacOS Tahoe.

## Building on MacOS

You'll need Qt6 and Poppler installed. Also a newer version of bison is required. You can install these via Homebrew with the following commands:

    brew install qt6
    brew install poppler
    brew install bison

Now link to the newer bison version:

    export PATH="/opt/homebrew/opt/bison/bin:$PATH"
    export LDFLAGS="-L/opt/homebrew/opt/bison/lib"
    
Back to Qt: Brew install doesn't add Qt binaries to the `$PATH` by default, so you may wish to either run:

    brew link --force qt6

or add `/usr/local/opt/qt/bin` to your `$PATH`. Once this is done, TikZiT can be built from the command line via:

    qmake -r
    make

Optional: To bundle the required libraries into `tikzit.app` and create a `.dmg` file, you can additionally run:

    ./deploy-osx.sh
