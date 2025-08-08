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
sudo apt-get install gz-harmonic
```

installation check:
```
gz sim
```
