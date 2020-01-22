# Fprime-CalPoly

# Benchmarking FPrime on the Beagle Bone Black
**Advisor**: Dr. Hadedy-Aly


**Summary**:

This is a senior project at **California Polytechnic University of Pomona** advised by Dr. Hadedy-Aly. The goal of the project is to benchmark the [F Prime (FÊ¹)](https://github.com/nasa/fprime) software on different types of hardware. The senior project group is currently split up to two groups. Group 1 is benchmarking the software on a Beagle Bone Black (BBB). Group 2 is benchmarking the software on a Pynq Z1.

This github will be dedicated to the development and benchmark of the Beagle Bone Black. The reasoning for this choice of hardware over the original Raspberry PI is the real time programmable GPIO pins on the BBB which allow for a more responsive system if time is a priority.



## Contents
1. [Technical Prerequisites](#tech-prereqs)
2. [Choosing an operating system](#choosing-os)
3. [Getting Started](#getting-started)



<!-- (#tech-prereqs) -->
## Technical Prerequisites
To properly utilize the F Prime and this project the user should have technica knowledge of the following.
1. Navigating and usage of Linux in a command line interface
2. Understanding of both C++ and Python(2 or 3)
3. Understanding the [F Prime Demo](https://github.com/nasa/fprime/blob/master/RPI/README.md) and the [F Prime README](https://github.com/nasa/fprime/blob/master/README.md)

<!-- (#choosing-os) -->
## Choosing an OS
The operating system that was chosen for the board was [ArchLinux](https://archlinuxarm.org/platforms/armv7/ti/beaglebone-black). In the link provided the Arch Linux website provides a easy to follow guide to boot Arch Linux on to your BBB.

Most UNIX flavors should be able to be ran on the Beagle Bone Black. Below will include a link directly to a Beagle Bone support site that shows supported unix flavors.
[Beagle Bone Black Supported Operating Systems](https://elinux.org/BeagleBone_Operating_Systems)

<!-- (#getting-started)-->
## Getting Started
### Communicating with the Beagle Bone Black
This part assumes you have installed the Linux on the MicroSD card and have a realiable power source. As well as the ethernet connected (NOTE: The beagle bone black will not properly connect to your computer unless it has a realiable 5v power source).

First boot up the beagle bone black and open PuTTY or your choice of SSH communication on your computer.

**For Windows Users**:

[PuTTY Download](https://www.putty.org/)

Run the program (Make sure to run as administrator)

Click SSH and and type this IP Address for the blank field:

```
192.168.7.2
```

**For Linux Users**:

To install SSH

```
sudo apt-get install ssh
```

Connect to the Beagle Bone Black by then:

```
sudo ssh 192.168.6.2
```

After you connecting the program (PuTTY) or (ssh) will ask you a question about the server's host key not being in your registry, click yes.

Type **root** for the login and return again for the password (empty).

You have now successfully connected to your Beagle Bone Black!

### Installing FPrime
After successfull communication with the Beagle Bone the next step is to install the proper libraries in order to run 
Fprime. 

Run the following commands in the ssh session:

**Update the System**

```
sudo pacman -Syu
```

**Update the Database**

```
sudo pacman -Syy
```

**Installing GitHub**

```
sudo pacman github
```

**Cloning the repo**

```
sudo git clone https://kylewong94/cpp-ece-seniorproject-2019_2020
```

**Installing required packages and libraries needed to run Fprime**

Run the following shell script file included in the following folder. 

```
sudo ./mk/os-pkg/archlinux-packages.sh
```


## copyrights
Copyright (c) 2009-2019, California Institute of Technology
("Caltech"). U.S. Government sponsorship acknowledged.

All rights reserved.

This product includes the GTest code Copyright, Google Inc.
This product includes cryptographic software written by  Eric Young (eay@cryptsoft.com)
This product includes pyparsing written by Paul T. McGuire
