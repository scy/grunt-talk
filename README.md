This is example code and some documentation for the [Grunt][] talk I held at [Cocomore][] in January 2014.

[Grunt]: http://gruntjs.com/
[Cocomore]: http://www.cocomore.com/

## How to install Node.js
Grunt is based on [Node.js][], therefore it needs a working Node installation.

[Node.js]: http://nodejs.org/

### On Ubuntu and Mint
Forget the Node versions that come with your distribution, they are most likely really old. Instead, install them from an unofficial repository.

    sudo aptitude install -y python-software-properties python g++ make
    sudo add-apt-repository -y ppa:chris-lea/node.js
    sudo aptitude update
    sudo aptitude install nodejs

### On other distributions
Check whether your distribution comes with a recent enough version of Node (hint: Debian doesn't). If it does, install that. If not, build from source!

You need Python, a C++ compiler and make, on Debian you can do `sudo aptitude install python g++ make`, on others you're on your own.

Then, run this:

    cd $(mktemp --tmpdir -d nodejs-install-XXXXXXX)
    wget -O - http://nodejs.org/dist/node-latest.tar.gz | tar xz && cd node-v* && ./configure && make -j5 && sudo make install && rm -rf $PWD && cd -

(This is just a short version of the installation procedure.)

### On a Mac
Use the [official installer][node-download] or [Homebrew][] (and then `brew install node`).

[node-download]: http://nodejs.org/download/
[Homebrew]: http://brew.sh/

### On Windows
Use the [official installer][node-download].

## How to install Grunt
What you're going to do here is just to install the `grunt` _command_. The actual Grunt library, as it is usual for Node projects, will be installed locally in each project's directory, in the version the project asks for.

Installing `grunt` is easy, now that we have Node (and with it, the _Node.js Package Manager_, `npm`):

    sudo npm install -g grunt
