# Strawberry Manual v4

This repository contains the manual for Strawberry version 4.x.

## Build environment

### On Debian Testing:

    $ sudo apt-get install python2.7 python-setuptools
    $ sudo easy_install sphinx

### On Mac OS X

The following is based on [Mac Ports](http://www.macports.org/install.php).

	> sudo port install python27
	> sudo port install sphinx_select

### On Windows

Ask Marc. He has done it before.

## Usage

If you would like to check locally if the manual pages you have created are looking as expected, do the following

1. Change to the directory where you have cloned the Git "Strawberry Manual" repository.
2. Type "make html" in the console/terminal
3. Check out the *\_build/html* directory.

If you push the Git repository back to /devhq/ the content will be automatically make'ed and you can access the "Strawberry Manual" at [docs.flavoursys.lan](http://docs.flavoursys.lan).
