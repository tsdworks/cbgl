# Install and run natively

This package was tested and works under Ubuntu 20.04 and ROS Noetic. You will need [`csm`](https://github.com/AndreaCensi/csm), `CGAL 4.7` and `fftw3` as dependencies. 

## Install Libraries

```sh
sudo apt update
sudo apt install -y ros-noetic-csm* libcgal* libfftw3*
```

## Compile 

```sh
cd ~
mkdir catkin_ws
cd catkin_ws
mkdir src
cd src
git clone https://github.com/tsdworks/cbgl.git
cd ..
catkin_make
```

## Run

### Configurations

See params_cbgl.yaml, params_csm.yaml and params_fsm.yaml in ~/catkin_ws/src/cbgl/cbgl/configuration_files

### Launch


```sh
roslaunch cbgl cbgl.launch
```

### Call

Launching `cbgl` simply makes it go into stand-by mode and does not actually execute global localisation. To do so simply call the provided service

```sh
rosservice call /global_localization
```
