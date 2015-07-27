Makerthings Server
=======================

### Introduction
The Makerthings server is based on openHAB and all documentation of openHAB is applied. Makerthings server runs on Raspberry Pi and connected to certain items, e.g. RGB strip, power switch, etc, to control them. You can download  [Makerthings app](https://play.google.com/store/apps/details?id=me.willowcheng.makerthings) to connect Makerthings server, or, open website [http://137.122.51.94:8080/openhab.app](http://137.122.51.94:8080/openhab.app) (only available when you are in University of Ottawa school network)

### Features
- Integrate with GPIO binding for Raspberry Pi for controlling GPIO based items, e.g. RGB strip, power switch (check important settings in Raspberry Pi)
- Integrate Dropbox Synchronization for backup systen folder
- Integrate Yahoo weather to display temperature and humidity
- Play music from preset online music list
- Support My.OpenHab Cloud data service for accessing logs and notification management for mobile devices
- Support voice control feature with preset commands

### Get Started
1. Download zip file
2. For Windows users, excute `start.bat`. For Mac and Linux users, navigate to your server root folder and use command `sudo sh start.sh`
3. Open web browser and enter URL [http://localhost:8080/openhab.app](http://localhost:8080/openhab.app)
4. You're ready to play around. Remember to get [Makerthings](https://play.google.com/store/apps/details?id=me.willowcheng.makerthings) Android app to have your things on your phone

### Development
1. Download openHAB Designer application
  - Download for [Windows](https://bintray.com/artifact/download/openhab/bin/distribution-1.7.0-designer-win.zip)
  - Download for [OS X](https://bintray.com/artifact/download/openhab/bin/distribution-1.7.0-designer-macosx64.zip)
  - Download for [Linux 64-bit](https://bintray.com/artifact/download/openhab/bin/distribution-1.7.0-designer-linux64bit.zip) | [Linux 32-bit](https://bintray.com/artifact/download/openhab/bin/distribution-1.7.0-designer-linux.zip)
2. Open openHAB Designer application and select configurations folder (`OpenHab/configurations`) in Configurations
3. If you are completely new, I would suggest you go through the [starter webniar](http://www.element14.com/community/videos/12763/l/home-automation-at-your-fingertips-with-eclipse-smarthome-and-openhab) for openHAB which gives you the tutorial how to develop step by step
4. Under `OpenHab/configuration` folder, development will be made on `Items`, `Persistence`, `Rules`, `Scripts`, `Sitemaps` and `openhab.cfg`
5. Check [OpenHab Home](https://github.com/openhab/openhab/wiki) to get ideas of how those things connected and cooperate with each other
6. For implementing binding, check [How To Implement A Binding](https://github.com/openhab/openhab/wiki/How-To-Implement-A-Binding). For advanced developers, checking [How To Implement An Action](https://github.com/openhab/openhab/wiki/How-To-Implement-An-Action)

### Development in Raspberry Pi
1. Raspberry Pi runs on Linux system can also run openHAB server. By default, Raspbian system is suggested, you can find the download and how to write image into SD card from [Download - Raspberry Pi](https://www.raspberrypi.org/downloads/)
2. The easier way to develop server is downloading Linux version of openHAB designer, [Linux 64-bit](https://bintray.com/artifact/download/openhab/bin/distribution-1.7.0-designer-linux64bit.zip) | [Linux 32-bit](https://bintray.com/artifact/download/openhab/bin/distribution-1.7.0-designer-linux.zip)
3. Use the same development method as Windows or Mac
4. If you want to edit server in Windows/Mac and upload your files directly to Raspberry Pi. FTP tool is suggested and SSH should be enabled - [SSH (Secure Shell) - Raspberry Pi](https://www.raspberrypi.org/documentation/remote-access/ssh/), [FileZilla](https://filezilla-project.org) is free for Windows/Mac. Alternatively, using Github to keep your work between laptop and Raspberry Pi is even better. (Push work to Github and pull changes to Raspberry Pi)
5. Use terminal to navigate to OpenHab server directory and use `sudo sh start.sh` to run your server
6. Enable SPI and I2C support for using GPIO
7. Unexport GPIO before starting server, a more intelligent way is using [WiringPi](http://wiringpi.com/the-gpio-utility/) in terminal
  - `cd /sys/class/gpio`
  - `sudo echo 17 > unexport` (17 may be altered depending on which pin number will be used)
8. Install native JNA library via `apt-get install libjna-java`
9. If you want to run server automatically once you start Raspberry Pi, Check [Linux OS X - openhab](https://github.com/openhab/openhab/wiki/Linux---OS-X)

---------------
Liu Cheng, University of Ottawa
