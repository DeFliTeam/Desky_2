# Desky_2
Build Instructions for Raspbian/Ubuntu based system with rotator for satellite tracking  

**2 Elements** 

Step 1 Build Rotator 
Step 2 Use RPi 3 + to build controller and install software


**Desky Rotator** 

DeSKy Rotator is a very cheap, modular and smart satellite rotator. It has the ability to automatically and manually control a load device such as an antenna for satellite communications enabling a user to easily construct a device at home for use on the DESKY Network. 

The GUI has 2 main modes. A manual mode that a user can use to manually track a celestrial body using a mouse on the system. this provides a solid flexiblity for serach and observation of the sky. The second mode is the automatic mode. This mode allows the user to set a satellite to track whenever the satellite comes into view. This can be used to automatically transmit or receive information from satellite when it rises and before setting. This uses a kernal interrupt so as not to monopolize CPU resources. Ability to search and predict which and when satellites are coming over your location anywhere on earth.


<a href="https://ibb.co/f9p7LhL"><img src="https://i.ibb.co/PMh8070/Cloud-Internet.png" alt="Cloud-Internet" border="0"></a> 

<a href="https://ibb.co/P5XWKGP"><img src="https://i.ibb.co/FBZY24y/Network-Setup.png" alt="Network-Setup" border="0"></a>


**Software** 

The main coding language is C/C++ and as such, a basic understanding of C/C++ is required. The software engineering heavily relies on a GUI development. Qt development package is the ideal package 

*Main dependencies* 

# C++14

- sudo apt-get install -qq g++-6
- sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-6 90
- sudo apt-get --yes install qt5-default qt514-meta-full qt514tools qt514webengine qt514base qt514imageformats qt514svg libqt5webkit5-dev qt514charts-no-lgpl qt514xmlpatterns
- sudo apt-get install zlib1g-dev g++ cmake doxygen graphviz libboost-all-dev libssl-dev
# only on the raspberry pi
- sudo apt-get install wiringpi


**Device and OS** 

The device used for the project is a raspberry pi 3 B with the raspbian (GNU/Linux) operating system installed on it. 

**SDR Kit** 


    Custom antenna
    RTL-SDR
    RG58 50ohm cable
    SMA connectors

**Build and Install** 

git clone https://github.com/Ahmad138/SatRot.git

# To install main-GUI on ubuntu
cd satrot/Software/SatRot-GUI
mkdir build && cd build
qmake ..
make

sudo make install
cd GUI-Main
./GUI-Main

# To install RotorDriver-GUI on raspberrypi 3
cd satrot/Software/RotorDriver-GUI
mkdir build && cd build
qmake ..
make

sudo make install
cd RotorDriver
./RotorDriver

# To run tests, cd into each module test you want to perform and run it. for example:
cd build/apiTest
make check
