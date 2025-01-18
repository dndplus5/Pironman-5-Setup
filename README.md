## Pironman-5-Setup

### Pironman 5

### Pironman 5 case

## Quick Links:

    Pironman 5
        About Pironman5
        Links
        Installation
        Usage
        Update
        Compatible Systems
            Ubuntu 24.04 server eth0 and wifi not work
         
  

About Pironman5
Links



Installation

For systems that don't have git, python3 pre-installed you need to install them first

sudo apt-get update
sudo apt-get install git python3 -y

Execute the installation script

cd ~
git clone https://github.com/sunfounder/pironman5.git
cd ~/pironman5
sudo python3 install.py

Usage

Update

https://github.com/sunfounder/pironman5/blob/main/CHANGELOG.md
Compatible Systems

Operate Systems that passed the test on the Raspberry Pi 5:
Operate System 	Release Date 	Compatible
Raspberry Pi OS Desktop - bookworm (64 bit) 	2024-11-19 	✅
Raspberry Pi OS Desktop - bookworm (32 bit) 	2024-11-19 	✅
Raspberry Pi OS Full - bookworm (64 bit) 	2024-11-19 	✅
Raspberry Pi OS Full - bookworm (32 bit) 	2024-11-19 	✅
Raspberry Pi OS lite - bookworm (64 bit) 	2024-11-19 	✅
Raspberry Pi OS lite - bookworm (64 bit) 	2024-11-19 	✅
Ubuntu Desktop 24.04.1 LTS (64 bit) 	2024-08-29 	✅
Ubuntu Server 24.04.1 LTS (64 bit) 	2024-10-10 	✅
Ubuntu Desktop 24.10 (64 bit) 	2024-10-10 	✅
Ubuntu Server 24.10 (64 bit) 	2024-08-29 	✅
Kali Linux 	2024-08-27 	✅
Home Assistant OS 14.0 	2024-12-03 	✅
Homebridge bookworm (64 bit) 	2024-05-03 	✅
Homebridge bookworm (64 bit) 	2024-05-03 	✅
Batocera Linux 	2024-07-31 	✅
Ubuntu 24.04 server eth0 and wifi not work

https://www.reddit.com/r/Ubuntu/comments/1d0s8v5/ubuntu_2404_server_on_my_raspberry_pi_5_and_eth0/
Debug

Clone the dependency you want to debug or edit

git clone https://github.com/sunfounder/pironman5.git
git clone https://github.com/sunfounder/pm_dashboard.git
git clone https://github.com/sunfounder/pm_auto.git
git clone https://github.com/sunfounder/sf_rpi_status.git

Make adjustments, and manually install the package

cd ~/pironman5 && sudo /opt/pironman5/venv/bin/pip3 uninstall pironman5 -y && sudo /opt/pironman5/venv/bin/pip3 install .
cd ~/pm_dashboard && sudo /opt/pironman5/venv/bin/pip3 uninstall pm_dashboard -y && sudo /opt/pironman5/venv/bin/pip3 install .
cd ~/pm_auto && sudo /opt/pironman5/venv/bin/pip3 uninstall pm_auto -y && sudo /opt/pironman5/venv/bin/pip3 install .
cd ~/sf_rpi_status && sudo /opt/pironman5/venv/bin/pip3 uninstall sf_rpi_status -y && sudo /opt/pironman5/venv/bin/pip3 install .

Start/stop the service for debug

sudo systemctl stop pironman5.service
sudo systemctl start pironman5.service
sudo systemctl restart pironman5.service
sudo pironman5 start

sudo /opt/pironman5/venv/bin/python3

About 


Contact us

website:

E-mail: 
