Makerspace Internet of Things (OpenHab)
=======================


## Get Started
1. Download zip file
2. For Windows users, excute `start.bat`. For Mac and Linux users, use command `sh start.sh`
3. Open web browser and enter URL [http://localhost:8080/openhab.app?sitemap=demo](http://localhost:8080/openhab.app?sitemap=demo)

## Important Settings for Raspberry Pi
1. Enable SPI and I2C support
2. Unexport GPIO before starting server
  - `cd /sys/class/gpio`
  - `sudo echo 17 > unexport` (17 may be altered depending on which pin number will be used)

## Features
- Integrate with GPIO binding for Raspberry Pi
- Integrate Dropbox Synchronization for backup
- Integrate Yahoo and Forecast IO API for weather data
- Support My.OpenHab Cloud data service for accessing logs and notification management for mobile devices
- Support voice control feature with preset commands

Liu Cheng, University of Ottawa
