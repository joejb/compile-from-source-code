# compile-from-source-code
Build a program from source and install it on your system.

You don’t have to be a programmer to compile a program from source code and install it on your system
You only have to know the basic few commands, you can build from source code.

#Installing the Required Software

The build-essential package  installs the basic software you’ll need to compile from source, like the GCC compiler and other utilities. Install it by running the following command in a terminal:

    $ sudo apt-get -y install build-essential

#Getting a Source Package

Now you’ll need your desired application’s source code. 
These packages are usually in compressed files with the .tar.gz or .tar.bz2 file extensions.

Locate the program’s .tar.gz or .tar.bz2 file and save it to your computer.
A .tar.gz or .tar.bz2 is like a .zip file.

To use it, we’ll have to extract its contents.
Use this command to extract a .tar.gz file:

    S tar -xzvf file.tar.gz

Or use this command to extract a .tar.bz2 file:

    S tar -xjvf file.tar.bz2
    
    
