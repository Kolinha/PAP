<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<p align="center">
   <img src="images/logo.jpg" alt="Logo" width="200" height="200">

  <h3 align="center">DextroBot</h3>

  <p align="center">
    3D printed omni-directional robot with mechanum wheel powered by ROS
    <br />
    <a href="https://github.com/AntoBrandi/DextroBot/"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/AntoBrandi/DextroBot/">View Demo</a>
    ·
    <a href="https://github.com/AntoBrandi/DextroBot/issues">Report Bug</a>
    ·
    <a href="https://github.com/AntoBrandi/DextroBot/issues">Request Feature</a>
  </p>
</p>

[![Product Name Screen Shot Real][product-screenshot-real]](https://example.com)

<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Built With](#built-with)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Usage](#usage)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

This project aim is to build an omni-directional robot for the indoor navigation and mapping using inexpensive sensors such as ultrasonic sensors.
Furthermore, it implements some basics human tracking and following functionalities using the raspberry pi camera mounted on its top. In order to activate or deactivate
this tracking functionalities, a speech recognition module has been implemented. This module can run on any computer with a microphone that is connected to the same Wi-Fi network 
of the robot.

### Built With
This robot is powered by:
* Raspberry Pi 4
* Arduino UNO
* CNC Shield
* Nema 17 Stepper Motor
* drv8825 Stepper Motor Driver
* 11.1V 3s LiPo Battery
* LM2596 DC-DC converter
* Raspberry Pi Camera
* HC-SR04 Ultrasonic Sensors
* MPU6050 IMU

And is controlled by:
* ROS Kinetic

[![Product Name Screen Shot Exploded][product-screenshot-exploded]](https://example.com)


<!-- GETTING STARTED -->
## Getting Started

Once it's printed and assembled according and connected, there are few configuration to be made in both Raspberry Pi side and Arduino UNO.

### Prerequisites

Make sure you install correctly the following required tools before continuing
* Install Ubuntu 16.04 on Raspberry Pi 4
Use the [Ubiquity Robotics](https://downloads.ubiquityrobotics.com/pi.html) Raspberry Pi images that cames along with a lot of pre-installed functionalities such as ROS kinetic, ssh server, GPIO and camera
drivers
* Install missing ROS libraries. Some libraries that are used in this project are not in the standard ROS package. Install them with:
```sh
sudo apt-get install ros-kinetic-rosserial
```
```sh
sudo apt-get install ros-kinetic-rosserial-arduino
```
```sh
sudo apt-get install ros-kinetic-rviz-imu-plugin
```
* Install VS Code and Platform IO extension on your PC in order to build and load the Arduino code on the device


### Installation

1. Clone the repo
```sh
git clone https://github.com/AntoBrandi/DextroBot.git
```
2. Build the ROS workspace
```sh
cd ~/DextroBot/ROS/dextrobot_ws
```
```sh
catkin_make
```
3. Source the project
```sh
sudo nano ~/.bashrc
```
And add the following at the end of the document
```sh
source ~/DextroBot/ROS/dextrobot_ws/devel/setup.bash
```
4. Connect the Arduino UNO on your PC with VS Code and Platform IO. Open the [folder](https://github.com/AntoBrandi/DextroBot/tree/master/ROS/dextrobot_ws/src/dextrobot_controller/src/arduino/wheel_controller)
containing the code for the Arduino wheel control and load the main.cpp to the Arduino.



<!-- USAGE EXAMPLES -->
## Usage

To launch the ROS enviroment on the Raspberry Pi use
```sh
roslaunch dextrobot_bringup dextrobot_complete.launch view_imv:=true
```
With optional parameters
* **view_imv**: to display the motion vectors detected by the raspberry pi camera
* **launch_rviz**: to display the readings coming from the sonar sensors and the imu





<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Antonio Brandi - [LinkedIn]([linkedin-url]) - antonio.brandi@outlook.it

My Projects: [https://github.com/AntoBrandi](https://github.com/AntoBrandi)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [Ubiquity Robotics Raspberry Pi Images](https://downloads.ubiquityrobotics.com/pi.html)
* [Ubiquity Robotics raspicam_node](https://github.com/UbiquityRobotics/raspicam_node)
* [How To Mechatronics mechanum wheel](https://howtomechatronics.com/)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/antonio-brandi-512166bb/
[product-screenshot]: images/solidworks.jpg
[product-screenshot-exploded]: images/solidworks-exploded.jpg
[product-screenshot-real]: images/robot.jpg
