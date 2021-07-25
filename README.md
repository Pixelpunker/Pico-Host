# Pixelpunker's PICO-8 Installer

## How to install
### Prerequisites
- Download [Batocera for the CM3](https://batocera.org/download), scroll down to "Raspberry Pi CM3/CM3+". Write it to a MicroSD card using the [Raspberry Pi Imager](https://www.raspberrypi.org/software/). Use a SD card marked A1 or A2 (Application class).

- Download [GPM280 DTBO](https://www.waveshare.com/wiki/File:GPM280_DTBO.zip) and unzip it to the overlays directory. Edit config.txt and add the following lines to the end of the file:

``` 
dtparam=spi=off
dtparam=i2c_arm=off
gpio=0-27=a2
dtoverlay=dpi24
enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
display_rotate=3
dpi_output_format=0x7F217
hdmi_timings=480 0 26 16 10 640 0 25 10 15 0 0 0 60 0 32000000 1
extra_transpose_buffer=2
hdmi_ignore_edid=0xa5000080
dtoverlay=gpm280-pwm-audio
``` 

### Prepare Batocera
- Turn on the Game Pi Micro. Once you are on the home screen, access the menu with the menu key (start) and connect to your local Wi-Fi under Network Settings/Hostname
- Turn on security under System Settings/Security
- Now reboot under Quit/Restart System. Write down your IP address under Network Settings. Now write down your password under System Settings/Security.

### Finish Setup

Login to your Lexaloffle-Account and download the PICO-8 zip file for the Raspberry Pi to your downloads folder.


Enter this command in [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701), Mac Terminal or a Linux Terminal.

``` 
scp ~/Downloads/pico-8*_raspi.zip root@192.168.178.YOUR_IP:/userdata/
```

It will ask for your password you noted earlier. Now type (and enter your password again)
```
ssh root@192.168.178.YOUR_IP
cd /userdata/
wget https://github.com/Pixelpunker/Pico-Host/releases/download/0.1/install-pico8.sh
chmod +x install-pico8.sh
./install-pico8.sh
```
After successful installation the system reboots.

<img src="https://github.com/Pixelpunker/Pico-Host/blob/master/images/mainp8.png"></img>

Your new home screen.

## Features

PICO-8 is properly installed with the following additional features:
- Sharp scaling
- Left and right triggers additionally function as ❎ and ⭕
- Press select for a screenshot
- Hold select for 0.5 s for a video

<img src="https://github.com/Pixelpunker/Pico-Host/blob/master/images/subp8.png"></img>

Launch PICO-8 in splore mode by choosing 'console' You can also swap controls between "Xbox style" ❎⭕ (which is the PICO-8 default) or "Nintendo Style" ⭕❎.


<img src="https://github.com/Pixelpunker/Pico-Host/blob/master/images/screensh.png"></img>

Browse screenshots and gifs you took with the select key directly on your Game Pi Micro.


<img src="https://github.com/Pixelpunker/Pico-Host/blob/master/images/BJgqjJ.gif"></img>

Play PICO racer using the shoulder buttons.

### Controls
<img src="https://github.com/Pixelpunker/Pico-Host/blob/master/images/40_Shortcuts.png"></img>

You can test the (swapped) controls by lauching API.p8.

Have fun. The fantasy console is no longer a fantasy. It's in your hands.

## Additional tips

You can browse the latest and greatest games via splore. Just launch 'console'. You can also use the search function inside splore without a keyboard. Simply move the dpad up or down to enter letters.
