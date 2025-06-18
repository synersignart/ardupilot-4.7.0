# ArduPilot Project

# build Terminal 

create your workspace folder in the home folder
    0    cd workspace

in your ubutnu terminal

    0    sudo apt update
    1    sudo apt-get update
    2    sudo apt-get install git
    3    sudo apt-get install gitk git-gui

you might need to Fork the Ardupilot repository into your own github profile githum user id

    4    git clone --recurse-submodules https://github.com/your-github-userid/ardupilot
         cd ardupilot

 this creates a Ardupilot folder at your root

 create new folder and name it (build)
         
From the cloned ardupilot directory : cd workspace/ardupilot

    5   Tools/environment_install/install-prereqs-ubuntu.sh -y    
    6   . ~/.profile

Then Log out and Log in again to save

Now you should be able to build with waf as described in BUILD.md. For example, for a Copter build for the MatekH743 board:

    7     Your Target boar

          ./waf configure --board MatekH743 

          Your Vehicle Type

          ./waf copter
          ./waf heli
          ./waf plane
          ./waf rover
          ./waf sub
          ./waf blimp
          ./waf antennatracker

Cleaning

If there have been updates to some git submodules you may need to do a full clean build. To do that use:

Should waf not configure pop up
    8    python3 waf configure

# SHOULD THERE BE ERRORS

could not find program arm-none-eabi-ar error

    9    arm-none-eabi-cgg --version
    10    arm-none-eabi-g++ --version
    11    arm-none-eabi-size --version
    12    sudo apt-get install gcc-arm-none-eabi

to build your target you must first assign a ID then create a folder of your target board

board types.txt 
ardupilot/Tools/AP_bootloader


Folder of your Target board
ardupilot/libraries/AP_HAL_ChibiOS/hwdef


