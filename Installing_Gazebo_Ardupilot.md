# Installing Gazebo and Ardupilot Plugin

## Installing Gazebo Ionic

More Information at (https://gazebosim.org/docs/ionic/install_ubuntu/)

Preliminary Steps
```
cd ~
sudo apt-get update
sudo apt-get install lsb-release gnupg
```

Setup your computer so that it can get code from ROS Foundation
```
sudo curl https://packages.osrfoundation.org/gazebo.gpg --output /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
sudo apt-get update
sudo apt-get install gz-ionic
sudo apt install gz-ionic libgz-sim8-dev
sudo apt install rapidjson-dev libgz-math7-dev libgz-plugin2-dev libgz-transport13-dev libgz-msgs10-dev

```

installation check:
```
gz sim
```

## Plugin Download
```
cd
git clone https://github.com/ArduPilot/ardupilot_gazebo.git

sudo apt update
cd ardupilot_gazebo
mkdir build
cd build
cmake ..
make -j4
sudo make install
```
```
echo 'source /usr/share/gazebo/setup.sh' >> ~/.bashrc
```
Set paths for models:
```
echo 'export GAZEBO_MODEL_PATH=~/ardupilot_gazebo/models' >> ~/.bashrc
. ~/.bashrc
```

## OpenCV Issue
If you have OpenCV Issues:
```
sudo apt install libopencv-dev
```

## G-Streamer Issue
If you have G-Streamer Issues:
```
sudo apt install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev
```


