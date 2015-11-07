
## Introduction
A+ is a descendent of APL, see http://www.aplusdev.org/. This repository holds my attempt to build A+ on Ubuntu 14.04 LTS.

## Preparation
1. pull down the source code from this repository. This is mainly based on A+ 4.22-1 from http://www.aplusdev.org/Download/index.html with a few minor fixes.
1. install necessary packages
        apt-get install g++ make, xorg-dev xemacs21

## Build & Install 
1. create install directory
        sudo mkdir /usr/local/aplus/;
        sudo chown <your-login> /usr/local/aplus/;
        chmod 644 /usr/local/aplus/;
1. navigate to the top directory of the source tree, run 
        ./configure --prefix=/usr/local/aplus/
1. make -j4 install
1. verify that the build is successful,
        /usr/local/aplus/bin/a+; enter some A+ statement like "1+2" or "2*10"

## XEmacs Setup
1. install KAPL font. on Debian/Ubuntu it's easier to simply run
        apt-get install xfonts-kapl

1. add following line to your .emacs file
        (load "/usr/local/aplus/lisp.1/aplus")

1. when running XEmacs, use following environment to workaround some font issue in xemacs - there must be a better solution...
        unset XMODIFIERS; export LANG=C; xemacs &
        F4 to start up A+
        then Options->Font->Kapl to change to KAPL font.
