# Installing Ardupilot and MAVProxy Ubuntu 24.04

## Clone Ardupilot

In Home Directory:
```
cd~
sudo apt install git
git clone https://github.com/ArduPilot/ardupilot.git
cd ardupilot

```
## Install Dependencies
```
Tools/environment_install/install-prereqs-ubuntu.sh -y
```

Reload Profile
```
. ~/.profile
```

## Checkout latest copter build
```
git config --global url.https://.insteadOf git://
git checkout Copter-4.4.4
sudo apt install python3.11 python3.11-dev python3.11-venv python3.11-distutils
curl -sS https://bootstrap.pypa.io/get-pip.py | python3.11curl -sS https://bootstrap.pypa.io/get-pip.py | python3.11
git submodule update --init --recursive
```

Run SITL (Software In The Loop) once to set params:
```
git checkout master
git pull origin master
./waf distclean
./waf configure --board sitl
cd ~/ardupilot/ArduCopter
sim_vehicle.py -w
```

