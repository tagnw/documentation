# RoboRuckus Bootstrap
## Requirements

- Visual Studio Code
	- w/ Platform.io extension
- [Raspberry Pi OS Lite 64-bit ISO Image](https://www.raspberrypi.com/software/operating-systems/#raspberry-pi-os-64-bit)
- [Game Server Code](https://github.com/ShVerni/RoboRuckus/tree/master/PiReady)
- 8GB+ MicroSD

### Physical Items

- Programming Laptop
- Charger for laptop
- Raspberry Pi
- MicroSD Card
- Power supply for Pi
- Ethernet Cable
- Tablets for game control
- Robots
	- Batteries
- MicroUSB cable for programming robots
- Headset for voip (optional)

## Getting Started

1. Download the large files needed
	1. Visual Studio Code
	2. [Raspberry Pi OS Lite 64-bit](https://www.raspberrypi.com/software/operating-systems/#raspberry-pi-os-64-bit)
2. [Install the PlatformIO IDE extension for Visual Studio Code](https://docs.platformio.org/en/latest/integration/ide/vscode.html#installation)
	1. Open Visual Studio Code
	2. Either click on the extension icon (insert screenshot) or press `ctrl+shift+x` to open the extensions marketplace
	3. Search for "PlatformIO IDE"
	4. Click Install
3. [Install Raspberry Pi Imaging Utility](https://www.raspberrypi.com/software/)
	1. Download .deb file
	2. Install deb file
4. Image your MicroSD card
	1. Insert MicroSD card into computer
	2. Run "Imager"
	3. Select Operating System
		1. Other
		2. Raspberry Pi OS Lite (32-bit)
	4. Select MicroSD card as storage
	5. See screenshot[^1] for config settings (click on gear)
	6. Click "Write"
5. [Setup freshly imaged sd card w/ headless mode](https://www.raspberrypi.com/documentation/computers/configuration.html#setting-up-a-headless-raspberry-pi)
	1. Configure networking w/ wpa_supplicant.conf
	2. Copy PiReady/RoboRuckus to /home/pi/RoboRuckus (if on linux)
	3. Safely Eject
6. After booting and SSHing into the pi
	1. [Configure files for execution](https://www.roboruckus.com/documentation/setting-up-the-game/#Setting-Up-RoboRuckus)
	2. [Run the game using the browser UI](https://www.roboruckus.com/documentation/running-a-game/)
7. From your laptop
	1. Open Visual Studio Code
	2. Open as folder: `robotics/projects/arduino_ruckus_mm/Mbits/Ringbit Car/Ringbit_Car_PlatformIO`
	3. Trust us >:)
	4. Click on the checkmark on the bottom blue bar "Build"
	5. Should exit successfully, if it doesn't...Message Sam.
	6. `.pio/build/esp32dev/firmware.bin` is the OTA update file for fancy stuff
8. Connect to the raspberry pi via SSH
	1. `ssh pi@roboruckus.local`
9. Connect to robot
	1. Plug in to laptop
	2. Open Visual Studio Code
	3. Upload using ringbit car project
	4. DO NOT UNPLUG OR RESET UNTIL DUCK SHOWS UP!!!
10. Connect to randomly generated SSID `Ruckus_<numbers>`
	1. Wifi password is `RuckusBot` by default
	2. Captive portal should show up (sign in)
	3. Click on Configure WiFi
		1. Connect to same wifi as raspberry pi
		2. Use same IP and port as the pi (`ping roboruckus.local` from laptop if unsure of IP)
11. Connect to game server
	1. http://roboruckus.local:8082/setup
	2. [Tune robot(s)](https://www.roboruckus.com/documentation/running-a-game/#Tuning-the-Robots)
12. [Play!](https://www.roboruckus.com/documentation/running-a-game)

[^1]: ![[Screenshot from 2022-04-16 13-14-44.png]]
