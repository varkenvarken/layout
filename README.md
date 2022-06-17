# layout
My model railroad layout with JMRI on raspberryPi wit Digikeijs DR5000 + DR4024 + DR4088

# description
This repo basically documents my specific installation steps and will hold any layout and automation files that I will create.

# hardware
My layout is controlled by a Digikeijs DR5000. It is connected to a RaspberryPi 3B+ via USB that is running JMRI. On the layout there are server Digikeijs DR4024 servo controllers that drive the points (switches, turnouts) and DR4088CS current sensors that are used for block occupancy detection.

The DR5000 also offers Wifi and is set to the Z21 protocol so that I can control stuff directly with my Roco WLAN maus.

The RaspberryPi connects to my regular guest wifi network so panels and the like can be accessed by anyone with access to this guest network.

# schematic

TODO

# software

- Raspberry Pi OS (64 bit) compatible with Debian Bullseye released April 4, 2022 
- JMRI.4.99.10 (the latest test release as per June 12, 2022

# steps to create a Raspberry PI OS sd card

I used [the Raspberry Pi Imager](https://www.raspberrypi.com/software/) on Ubuntu.

- run it and select Raspberry Pi OS (64 bit)
  Not the full edition, because we do not need all that recommended software.
- In the settings I configured the following
  hostname: raspberrypi
  enable ssh (with password authentication. You can generate a certificate later if you like)
  set username and password (do not use the default pi, and select a fairly strong password)
  configure wireless lan (select SSID and password. My Raspberry Pi will not act an access point but connect to our guest network)
- choose storage (make sure you have a writeable microsd card in your reader and check that you select the right one!)
- write

# steps to configure JMRI of the RaspberryPI

```bash
sudo apt-get install openjdk-11-jdk
wget https://github.com/JMRI/JMRI/releases/download/v4.99.10/JMRI.4.99.10+Rdc754efff4.tgz
gunzip -c JMRI.4.99.10+Rdc754efff4.tgz | tar xvf
```    

# configuring the command station link
