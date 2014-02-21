<img src="https://raw.github.com/AOSPLUS/manifest/master/AOSPLUS.jpg">
===============

Getting Started
---------------

To get started with AOSPLUS, you'll need to get
familiar with [Git and Repo](http://source.android.com/download/using-repo).

Now, install those packages that are needed:

    sudo apt-get install git gnupg flex bison gperf build-essential \
    zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev \
    libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386 \
    libgl1-mesa-dev g++-multilib mingw32 tofrodos \
    python-markdown libxml2-utils xsltproc zlib1g-dev:i386

    sudo ln -s /usr/lib/i386-linux-gnu/mesa/libGL.so.1 /usr/lib/i386-linux-gnu/libGL.so

After that, we have to create the binary repository:

    mkdir ~/bin
    PATH=~/bin:$PATH
    curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
    chmod a+x ~/bin/repo

And finally, we create the folder where the source is going to be, you need at least 15gb of free space:

    mkdir AOSPLUS
    cd AOSPLUS

Downloading the sources
---------------

To initialize your local repository using the AOSPLUS trees, use a command like this:

    repo init -u git://github.com/AOSPLUS/manifest.git -b <branch>

Then to sync up:

    repo sync

Building
---------------

    . build/envsetup.sh && lunch

And select your device

    make bacon -j4

