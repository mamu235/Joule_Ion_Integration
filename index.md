---
title: Home
---

# Welcome to RoboJoule

We will be getting started with an ION MC motor controller, an Intel Joule, and Ubuntu to getthis project running.

1. Get an Intel Joule, flash the BIOS, and install Ubuntu. Those instructions can be found here: [https://sites.google.com/view/ubuntu-16-04-on-an-intel-joule/home](https://sites.google.com/view/ubuntu-16-04-on-an-intel-joule/home)

2. Once you have the Joule up and running, you will need to install [xfce](https://wiki.debian.org/Xfce), a Ubuntu desktop environment that is faster than Ubuntu Unity on the Joules. To do this follow these steps:

    * Open a Terminal on your Joule and enter `sudo apt-get install xfce4` and enter your password
    
Once this is completed, restart the Joule.
    
3. Next we will [install Qt Creator](https://www.qt.io/download), selecting the Open Source option. On our Linux based system, a `.run` file will be downloaded. As it is an executable, you will need to run the command `sudo chmod 777 FILENAME.run` where FILENAME is the file you've just downloaded. Once you have execution privileges you will simply run the file.

     * In the installer, you will skip the account creation and login step. Thgen you will select an installation destination. Next you will choose to install Qt 5.7.0 by selecting it from the expanded Qt list.
     
4. Installing [QtZeroConf](https://github.com/jbagg/QtZeroConf). Download the Repo however you choose. You will want to put the extracted files in your `/usr/local/lib/` directory of your Joule.
      * Now we need to install 'qmake'. This is done by running the following command in terminal; `sudo apt-get install qt5-qmake`
      * Now we Need to simply run `qmake` followed by `make` in the directory you've put the QtZeroConf files. Once this is done, you'll run the following command to cp the appropriate header files to the appropriate directory:
      * `sudo cp qzeroconf.h qzeroconfglobal.h qzeroconfservice.h /usr/local/include/`
      
5. Open Qt Creator, open the LAUPaletteWidget.pro file, and at the top go to Build > Run qmake, then go to Build > Build All.

6. Run the Program to start RoboClaw with Intel Joule!
