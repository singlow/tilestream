TileStream
----------
A high performance tile server and simple web viewer for [MBTiles][1] files.


Features
--------
- MBTiles-based tile server
- Minimal gallery view and map viewer for tiles
- Support for MBTiles interaction using [Wax][2]


Requirements
------------
- *TileStream client*
  - Tested: Chrome 6+, Firefox 3+, IE8+
  - May work: Opera 11
- *TileStream server*
  - Tested: Mac OS X 10.6, Ubuntu 10.04, Ubuntu 11.04
  - Tested: node 0.4.9
  - Tested: npm v1.0.3
  - At least 613MB memory
  - May work: Older versions, other POSIX-compliant systems


Installation: Mac OS X 10.6
---------------------------
Install [Xcode][3] for Mac OS X.

Install [node][4].

Install [npm][5]:

    curl http://npmjs.org/install.sh | sh

Install TileStream:

    npm install -g tilestream

This will install TileStream globally. If you want a local installation in
your current working directory, run the command without the `-g` option.

Start TileStream:

    tilestream

TileStream should now be accessible from a browser at `http://localhost:8888`.


Installation: Ubuntu 10.04
--------------------------
Install build requirements:

    sudo apt-get install curl build-essential libssl-dev libsqlite3-0 libsqlite3-dev git-core

Install node:

    git clone --depth 1 git://github.com/joyent/node.git
    cd node
    git checkout v0.4.9
    export JOBS=2 # optional, sets number of parallel commands.
    mkdir ~/local
    ./configure --prefix=$HOME/local/node
    make
    make install
    echo 'export PATH=$HOME/local/node/bin:$PATH' >> ~/.profile
    source ~/.profile

Install [npm][5]:

    curl http://npmjs.org/install.sh | sh

Install TileStream:

    npm install -g tilestream

This will install TileStream globally. If you want a local installation in
your current working directory, run the command without the `-g` option.

Start TileStream:

    tilestream

TileStream should now be accessible from a browser at `http://localhost:8888`.
If you intend to run TileStream as a server on a hostname or an IP rather than
as localhost, specify that hostname when you run TileStream:

    tilestream --host 127.0.0.1
    tilestream --host yourhost.com


Usage
-----
MBTiles files should be placed in the `~/Documents/MapBox/tiles` directory,
which is created at first run. Each tileset can be previewed at
`http://localhost:8888/map/[filename]` where `[filename]` is the name of the
tileset file without the `.mbtiles` extension.

Tileset filenames:

- May contain letters (lower or upper case), numbers, underscores or dashes.

        world-light.mbtiles
        control_room.mbtiles
        PartyLikeIts1999.mbtiles

- May not contain periods, spaces, non ASCII characters or other punctuation.

        World Light.mbtiles
        BlueWorld-1.0.mbtiles

To see the options available for use with TileStream, run

    tilestream start --help


Tests
-----
TileStream tests use [Expresso][6].

    npm install -g expresso
    cd tilestream
    npm test


Contributors
------------
- [Young Hahn][7]
- [Tom MacWright][8]
- [Will White][9]
- [Konstantin Käfer][10]
- [Dane Springmeyer][11]


[1]:http://mbtiles.org
[2]:https://github.com/mapbox/wax
[3]:http://developer.apple.com/technologies/tools/xcode.html
[4]:https://github.com/joyent/node/wiki/Installation
[5]:http://npmjs.org/
[6]:http://visionmedia.github.com/expresso
[7]:https://github.com/yhahn
[8]:https://github.com/tmcw
[9]:https://github.com/willwhite
[10]:https://github.com/kkaefer
[11]:https://github.com/springmeyer
