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

You’ll end up with a directory with the same name as your source code package.
Use the cd command to enter it.

#Resolving Dependencies

Once you’re in the extracted directory, run the following command:
(Note that some applications may not use ./configure. Check the “README” or “INSTALL” file in the application’s extracted folder for more specific instructions.)

    ./configure

(The ./configure command checks your system for the required software needed to build the program. The ./ part tells the Bash shell to look inside the current directory for the “configure” file and run it. If you omitted the ./, Bash would look for a program named “configure” in system directories like /bin and /usr/bin.)

Once ./configure completes successfully, you’re ready to compile and install the package.

#Compiling and Installing

Use the following command to compile the program:

    $ make

This process may take some time, depending on your system and the size of the program. 
If ./configure completed successfully, make shouldn’t have any problems. 
You’ll see the lines of text scroll by as the program compiles.
After this command finishes, the program is successfully compiled (but it’s not installed). 
Use the following command to install it to your system:

    sudo make install

It’ll probably be stored under /usr/local on your system. 
/usr/local/bin is part of your system’s path.
Don’t delete the program’s directory if you want to install it later.
You can run the following command from the directory to uninstall the program from your system:

    sudo make uninstall

Programs you install this way won’t be automatically updated by Ubuntu’s Update Manager, even if they contain security vulnerabilities. Unless you require a specific application or version that isn’t in Ubuntu’s software repositories, it’s a good idea to stick with your distribution’s official packages.

Hopefully the process of compiling your own Linux software isn’t so scary anymore.
