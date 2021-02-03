#### Installing tippecanoe on Windows
On Windows, a version of tippecanoe must be specially compiled from its source code so that it can run inside a program called Cygwin, which provides Linux-like functionality through a collection of Windows-native utilities (i.e., non-emulated).

1. Download [setup-x86_64.exe](http://cygwin.com/setup-x86_64.exe) from the Cygwin website.
2. There are several development tools that will need to be installed as Cygwin extensions. Fortunately, the Cygwin setup application can be operated from the Windows command line and it can download support files as requested, so it won't be necessary to install the components individually. Navigate to the Windows Download directory by typing

    `cd %userprofile%/Downloads`,

    then enter the following command to install Cygwin along with the necessary development tools:

    `setup-x86_64.exe -q -P zlib-devel,libsqlite3-devel,gcc-g++,make,gdal`

3. Open the newly installed Cygwin64 Terminal application when installation is complete.
    
4. Clone the tippecanoe source code from Github, by entering:

    `git clone https://github.com/mapbox/tippecanoe.git`

5. In Windows, the tippecanoe source code will have been saved within your Cygwin home directory at `C:\cygwin64\home\{your username}\tippecanoe`. Navigate to this directory and open the Makefile within using Wordpad (Notepad will format the line endings incorrectly).
6. Add the text `-U__STRICT_ANSI__` to the line reading `CXXFLAGS := $(CXXFLAGS) -std=c++11`, so that it reads:

    `CXXFLAGS := $(CXXFLAGS) -std=c++11 -U__STRICT_ANSI__`

7. Back in the Cygwin terminal, enter the tippecanoe directory by typing

    `cd tippecanoe`

8. Compile the tippecanoe source code by typing

    `make`

9. Finally, install the compiled program by typing

    `make install`

Tippecanoe is now ready for use, and the source directory at `C:\cygwin64\home\{your username}\tippecanoe` can be deleted if desired.
