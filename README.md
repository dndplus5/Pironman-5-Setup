## Pironman-5-Setup


Pironman 5 case

Quick Links:

- [Pironman 5](#pironman-5)
  - [About Pironman5](#about-pironman5)
  - [Links](#links)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Update](#update)
  - [Compatible Systems](#compatible-systems)
    - [Ubuntu 24.04 server eth0 and wifi not work](#ubuntu-2404-server-eth0-and-wifi-not-work)
    - [Debug](#debug)
  - [Fans and Lighting](#how-to)


## About Pironman5

## Links


- Documentation &emsp; <https://docs.sunfounder.com/en/latest/>

## Installation

For systems that don't have git python3 pre-installed you need to install them first

```bash
sudo apt-get update
sudo apt-get install git python3 -y
```

Execute the installation script

```bash
cd ~
git clone https://github.com/sunfounder/pironman5.git
cd ~/pironman5
sudo python3 install.py
```

## Usage

-

## Update

<https://github.com/sunfounder/pironman5/blob/main/CHANGELOG.md>

## Compatible Systems

Operate Systems that passed the test on the Raspberry Pi 5:

Operate System | Release Date | Compatible
:---   | :---: | :---: 
Raspberry Pi OS Desktop - bookworm (64 bit) | 2024-11-19 | &#x2705;
Raspberry Pi OS Desktop - bookworm (32 bit) | 2024-11-19 |  &#x2705;
Raspberry Pi OS Full - bookworm (64 bit) | 2024-11-19 |  &#x2705;
Raspberry Pi OS Full - bookworm (32 bit) | 2024-11-19 |  &#x2705;
Raspberry Pi OS lite - bookworm (64 bit) | 2024-11-19 |  &#x2705;
Raspberry Pi OS lite - bookworm (64 bit) | 2024-11-19 |  &#x2705;
Ubuntu Desktop 24.04.1 LTS (64 bit) | 2024-08-29 |  &#x2705;
Ubuntu Server 24.04.1 LTS (64 bit) | 2024-10-10 |  &#x2705;
Ubuntu Desktop 24.10 (64 bit) | 2024-10-10 |   &#x2705;
Ubuntu Server 24.10 (64 bit) | 2024-08-29 |   &#x2705;
Kali Linux | 2024-08-27 | &#x2705;
Home Assistant OS 14.0 | 2024-12-03 | &#x2705;
Homebridge bookworm (64 bit) | 2024-05-03 | &#x2705;
Homebridge bookworm (64 bit) | 2024-05-03 | &#x2705;
Batocera Linux | 2024-07-31 | &#x2705;

### Ubuntu 24.04 server eth0 and wifi not work

https://www.reddit.com/r/Ubuntu/comments/1d0s8v5/ubuntu_2404_server_on_my_raspberry_pi_5_and_eth0/


### Debug

Clone the dependency you want to debug or edit

```bash
git clone https://github.com/sunfounder/pironman5.git
git clone https://github.com/sunfounder/pm_dashboard.git
git clone https://github.com/sunfounder/pm_auto.git
git clone https://github.com/sunfounder/sf_rpi_status.git
```

Make adjustments, and manually install the package

```bash
cd ~/pironman5 && sudo /opt/pironman5/venv/bin/pip3 uninstall pironman5 -y && sudo /opt/pironman5/venv/bin/pip3 install .
cd ~/pm_dashboard && sudo /opt/pironman5/venv/bin/pip3 uninstall pm_dashboard -y && sudo /opt/pironman5/venv/bin/pip3 install .
cd ~/pm_auto && sudo /opt/pironman5/venv/bin/pip3 uninstall pm_auto -y && sudo /opt/pironman5/venv/bin/pip3 install .
cd ~/sf_rpi_status && sudo /opt/pironman5/venv/bin/pip3 uninstall sf_rpi_status -y && sudo /opt/pironman5/venv/bin/pip3 install .
```

Start/stop the service for debug

```
sudo systemctl stop pironman5.service
sudo systemctl start pironman5.service
sudo systemctl restart pironman5.service
sudo pironman5 start

sudo /opt/pironman5/venv/bin/python3
```

Fans and Lighting

```
usage: pironman5-service [-h] [-c] [-rc [RGB_COLOR]] [-rb [RGB_BRIGHTNESS]]
                        [-rs [{solid,breathing,flow,flow_reverse,rainbow,rainbow_reverse,hue_cycle}]] [-rp [RGB_SPEED]]
                        [-re [RGB_ENABLE]] [-rl [RGB_LED_COUNT]] [-u [{C,F}]] [-gm [GPIO_FAN_MODE]] [-gp [GPIO_FAN_PIN]]
                        [{start,stop}]

Pironman5

positional arguments:
  {start,stop}          Command

options:
  -h, --help            show this help message and exit
  -c, --config          Show config
  -rc [RGB_COLOR], --rgb-color [RGB_COLOR]
                        RGB color in hex format with or without # (e.g. #FF0000 or 00aabb)
  -rb [RGB_BRIGHTNESS], --rgb-brightness [RGB_BRIGHTNESS]
                        RGB brightness 0-100
  -rs [{solid,breathing,flow,flow_reverse,rainbow,rainbow_reverse,hue_cycle}], --rgb-style [{solid,breathing,flow,flow_reverse,rainbow,rainbow_reverse,hue_cycle}]
                        RGB style
  -rp [RGB_SPEED], --rgb-speed [RGB_SPEED]
                        RGB speed 0-100
  -re [RGB_ENABLE], --rgb-enable [RGB_ENABLE]
                        RGB enable True/False
  -rl [RGB_LED_COUNT], --rgb-led-count [RGB_LED_COUNT]
                        RGB LED count int
  -u [{C,F}], --temperature-unit [{C,F}]
                        Temperature unit
  -gm [GPIO_FAN_MODE], --gpio-fan-mode [GPIO_FAN_MODE]
                        GPIO fan mode, 0: Always On, 1: Performance, 2: Cool, 3: Balanced, 4: Quiet
  -gp [GPIO_FAN_PIN], --gpio-fan-pin [GPIO_FAN_PIN]
                        GPIO fan pin
```
