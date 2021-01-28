# rpi-eeprom for Ubuntu
This script is a port of rpi-eeprom-update to RPi Ubuntu server.

If you are using other distributions, you can edit `CHECK_DISTRIBUTION` and `BOOT_FS` in this script. 

Original script and firmwares are [here](https://github.com/raspberrypi/rpi-eeprom).

## Installation
### Step 1. Install `vcgencmd`
```
sudo add-apt-repository ppa:ubuntu-raspi2/ppa
sudo apt update
sudo apt install libraspberrypi-bin
```

### Step 2. Install
Get the `rpi-eeprom` script and put it where you want it(ex. /usr/local/bin/).
```
cd /usr/local/bin/
wget https://github.com/hazuki0x0/rpi-eeprom-ubuntu/raw/master/rpi-eeprom
chmod +x ./rpi-eeprom
```

## Usage
#### Update local repository
```
sudo rpi-eeprom update
```
#### You can upgrade your pi's eeprom, if update available.

Release note is [here](https://github.com/raspberrypi/rpi-eeprom/blob/master/firmware/release-notes.md).
```
sudo rpi-eeprom upgrade
```
if you need to reset the bootloader_config,
```
sudo rpi-eeprom upgrade --default_config
```
#### Change firmware release status

See also - [Firmware release status](https://www.raspberrypi.org/documentation/hardware/raspberrypi/booteeprom.md)
```
sudo rpi-eeprom config --channel [critcal, stable, beta]
```

## Uninstall
```
cd /usr/local/bin/(**installed-dir**)
sudo ./rpi-eeprom uninstall_rpi_eeprom_files
sudo rm ./rpi-eeprom
```
