# Getting started

## Prerequisites

## Install the required tools.

**Install the J-Link debugging tools**

Go to the [J-Link Website](https://www.segger.com/jlink-software.html?step=1&file=JLinkLinuxDEB64_5.12.3)
and download the 64-bit deb package for Linux. When downloaded, install with the following command:

` sudo dpkg -i ~/Downloads/jlink_*_x86_64.deb `

**Since the ARM embedded toolchain is 32-bits, we need to install some 32-bits libraries.**

` $ sudo apt install lib32ncurses5 `

**Install git-repo multi repository manager**

` sudo apt install repo `

**Miscellaneous**

` sudo apt install screen schedtool umake doxygen doxygen-gui doxygen-latex`


## Setting up Eclipse

Since Eclipse is the IDE used for this projects Eclipse needs to be installed and configured.

**Install Eclipse**

The umake tool will automatically install eclipse for you. 

` umake ide eclipse-cpp `

To make Eclipse work with the NRF5x, open Eclipse and install the GNU ARM Embedded plug-in:

**Help->Eclipse Marketplace..**

and search for *GNU ARM Eclipse* and click install.

To make be able to compile the projects with Eclipse, a system variable needs to be set:

**Project->Properties->C/C++** Build->Environment and add the variable SDK_ROOT
and set it to the root directory of your SDK and you are good to go.


## Download the SDK and and git repositories.

To download the SDK and all the repositories:

` git init -u https://github.com/ShoeSensor/manifest `

**Initialize the environment**

cd into the root of the SDK and execute:

` source envsetup.sh `

This set's the path and adds some useful bash functions.

## Compiling a projects

From the SDK root, cd into one of the apps e.g. *apps/nrf_ble* and compile it:

` mka DEBUG=1 `

mka is a function to compile parallel, this saves you some time.

## Generating documentation

Doxygen is the documenting tool used in this project, to generate the html and latex pages:

` mkdocs `

The output will be in documentation/html and documentation/latex.
