# compile-from-source-code

Build a program from source and install it on your system.
You don’t have to be a programmer to compile a program from source code and install it on your system
You only have to know the basic few commands, you can build from source code.

#Installing the Required Software

The build-essential package  installs the basic software you’ll need to compile from source, like the GCC compiler and other utilities. Install it by running the following command in a terminal:

    $ sudo apt-get -y install build-essential

#Getting a Source Package

Now you’ll need your desired application’s source code. 
The source code for software on Linux comes in the form of compressed tar files, which typically have either .tar.gz or .tar.bz2 extensions. A .tar.gz or .tar.bz2 is like a .zip file.

Locate the program’s .tar.gz or .tar.bz2 file and save it to your computer or know the URL (download link) to the tarball.
Once you have the URL, use ‘wget’ to fetch the tarball from command line.

    $ wget <URL (download link) to the tarball>

The above command will download the tarball into the current directory.

Next unpack the tarball in order to get access to the source code and other files. 
Depending on the extension, use one of the following commands:

Use this command to extract a .tar.gz file:

    $ tar -xzvf file_name.tar.gz

Or use this command to extract a .tar.bz2 file:

    $ tar -xjvf file_name.tar.bz2

You’ll end up with a directory with the same name as your source code package.

Use the cd command to enter it.

    cd file_name

#Read Install Documentation

Once the software source code is downloaded and extracted, the very first thing that one should do is to go through the documentation. This is a very important step that thoroughly would save you from most of the future problems. 
The documentation provides information about the software, changes since last version, links to more documentation, information regrading the author of the software, steps for compilation and installation of software etc. 
So we can see that lots of valuable information is present in the documentation.
This whole information is broadly divided into two files : ‘Readme’ and ‘Install’. 
While ‘Install’ covers all the information required for compilation and installation, all the other information is covered in the ‘Readme’ file. 
Please note that the name of file and it case may vary.

You can use the less command on the command line to read them:

    $ less INSTALL
        or
    $ less README

(press ‘q’ on your keyboard to quit) or just open them in your favorite text editor. 
The documentation may point you to other software that you need to install before you can install this package (“dependencies”)

#Configuration (Building)

Once the above step is over then we can assume that we have sufficient theoretical knowledge about this software and now we can move forward and configure the environment for compiling and installing the software on our system. 
Most of the packages come along with a configuration script that can be used for configuring the environment. 
The file name for configuration file is mostly ‘configure’. 

Once you’re in the extracted directory, run the following command:
(Note that some applications may not use ./configure. Check the “README” or “INSTALL” file in the application’s extracted folder for more specific instructions.)

    $ ./configure

(The ./configure command check and/or creates the build environment for the required software needed to build the program on your system. The ./ part tells the Bash shell to look inside the current directory for the “configure” file and run it. If you omitted the ./, Bash would look for a program named “configure” in system directories like /bin and /usr/bin.)

Once ./configure completes successfully, you’re ready to compile and install the package.

#Compiling

In the same directory use the following command to compile the program:

    $ make

This process may take some time, depending on your system and the size of the program. 
If ./configure completed successfully, make shouldn’t have any problems. 
You’ll see the lines of text scroll by as the program compiles.
After this command finishes, the program is successfully compiled (but it’s not installed). 

#Installing

Use the following command to install it to your system:

    $ sudo make install

It’ll probably be stored under /usr/local on your system. 
/usr/local/bin is part of your system’s path.
Don’t delete the program’s directory if you want to install it later.

#Uninstall

You can run the following command from the directory to uninstall the program from your system:

    $ sudo make uninstall

Programs you install this way won’t be automatically updated by Ubuntu’s Update Manager, even if they contain security vulnerabilities. Unless you require a specific application or version that isn’t in Ubuntu’s software repositories, it’s a good idea to stick with your distribution’s official packages.

Hopefully the process of compiling your own Linux software isn’t so scary anymore.
