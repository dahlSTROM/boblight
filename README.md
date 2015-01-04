# Boblight

This is Boblight repository based on [Boblight](https://code.google.com/p/boblight/) source code.
This source code compiles on Linux, OSX and Windows.


## Changes from official source code

* Build environment cleanup
* Full support for Windows build environment under [Cygwin](https://www.cygwin.com/)

## Build

### Linux

Prepare the build environment

	sudo apt-get install -y build-essential autoconf libtool libusb-1.0-0-dev portaudio19-dev git 

Clone this repository

	git clone https://github.com/dahlSTROM/boblight

Change directory

    cd boblight
	
Run the following commands to set up build environment and build boblight

	./autogen.sh
	./configure --without-x11 --prefix=/usr
	make
	
Set up your configuration file as described in the [Boblight wiki](https://code.google.com/p/boblight/wiki/boblightconf). 

Run boblightd by issuing the following command

	./src/boblightd

Alternatively you can supply your own config file manually, for example

	./src/boblightd -c ./conf/lightpack.conf


Alternatively you can run boblightd with sudo.

If you want to install boblight to your system run the following command:

	sudo make install

Then follow the guide in the Wiki to [automatically start boblightd](https://github.com/arvydas/boblight/wiki/Automatically-starting-boblightd-on-Linux) when OS starts.

### OSX

Prepare the build environment

	brew install autoconf automake libtool libusb git

Clone this repository

	git clone https://github.com/dahlSTROM/boblight

Change directory

  cd boblight
	
Run the following commands to set up build environment and build boblight

	./autogen.sh
	./configure --without-x11 --without-portaudio
	make
	
Set up your configuration file as described in the [Boblight wiki](https://code.google.com/p/boblight/wiki/boblightconf). 

Run boblightd by issuing the following command

	./src/boblightd

Alternatively you can supply your own config file manually, for example

	./src/boblightd -c ./conf/lightpack.conf

### Windows

Building under Windows requires Cygwin environment. Prepare it by installing [Cygwin](https://www.cygwin.com/) together with the following additional packages

* make
* autoconf
* automake
* libtool
* gcc-g++
* libusb1.0-devel
* git

Open Cygwin shell and clone this repository

	git clone https://github.com/dahlSTROM/boblight

Change directory

    cd boblight
	
Run the following commands to set up build environment and build boblight

	./autogen.sh
	./configure --without-portaudio --without-x11
	make

Set up your configuration file as described in the [Boblight wiki](https://code.google.com/p/boblight/wiki/boblightconf). 

You can run boblightd.exe from the Cygwin environment by executing the following command

	./src/boblightd.exe

Alternatively you can supply your own config file manually, for example

	./src/boblightd.exe -c ./conf/lightpack.conf

If you want to run Boblightd.exe as standalone application without Cygwin environment, you will need the following files

	./src/.libs/boblightd.exe
	/bin/cyggcc_s-1.dll
	/bin/cygstdc++-6.dll
	/bin/cygusb-1.0.dll
	/bin/cygwin1.dll


## License

[GNU GPL v3](http://www.gnu.org/licenses/gpl.html)
           
## Author

* [Bob](https://code.google.com/u/105397595332940693856/)

## Maintainer

* Arvydas Juskevicius - [http://twitter.com/arvydev](http://twitter.com/arvydev)
