---
layout: post
title: "Raspberry Pi robot with vision and speech on ROS"
date: "2015-05-29"
type: post
published: true
status: publish
tags: robot raspberry-pi LEGO ROS
---

After having played with Lego Mindstorms NXT, this is my first "real" robot project.

I used the [Raspberry Pi](https://www.raspberrypi.org/ "Raspberry Pi") at the heart of my [KANO](http://www.kano.me/ "KANO") to build a little robot.  It is based on the "[Raspberry Pi camera robot](http://www.dawnrobotics.co.uk/raspberry-pi-camera-robot-chassis-bundle/ "Raspberry Pi camera robot")" of Dawn Robotics (2WD Dagu Magician chassis), to which I attached the speaker shipped with KANO.

My long-term goal is to build a robot platform like the NAOqi OS running on [NAO](https://www.aldebaran.com/en/humanoid-robot/nao-robot "NAO robot") or [Pepper](https://www.aldebaran.com/en/a-robots/who-is-pepper "Pepper robot").  These wonderful robots of Aldebaran robotics inspire me.

But let's start small.

**Installing ROS on the Pi and OS X**

Building the Raspberry Pi camera robot was relatively simple, based on the video and blog post guidance from Dawn Robotics.

I then installed [Raspbian](https://www.raspbian.org/ "Raspbian: Debian OS for Raspberry Pi") on my Pi, very simple.  Next, I started installing [ROS](http://www.ros.org/ "ROS") (Robot Operating System) -the "Indigo" distro- on the Pi, following [these instructions](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Indigo%20on%20Raspberry%20Pi "How to install ROS Indigo on Raspberry Pi").  This was a little trickier, but came out pretty well after all.

The next step was to install ROS on my Mac to control my robot remotely.  This is where the plan started to break: as mentioned on the ROS wiki, OS X support is _experimental_.  After a lot of wizzling and fiddling, I gave up, and decided to go for plan B: install Virtual Box on my Mac, with Ubuntu.  That was so much easier, because ROS installs mostly out-of-the-box on Ubuntu through apt-get.

After some network issues to allow my Virtual Box VM communicating with the Pi, I finally could run ROS remotely.  ROS core on the VM and a bunch of nodes on the Pi.

**Programming the robot**

Here is what my robot does:

- It just sets a fixed speed on the wheel motors (about 10cm/sec)
- It uses computer vision to analyse its own trajectory.  It will detect if it drifts to the left or to the right.
- If a drift is detected, the robot will speak out "Left" or "Right" (by playing a wav file).

Here are the nodes I pulled together:

- [rosberrypi\_cam](https://github.com/dlaz/rosberrypi_cam "rosberrypi_cam"): great little module by Dan Lazewatsky based on RaspiCam\_Cv (I had first tried [raspicam\_node](https://github.com/fpasteau/raspicam_node "raspicam_node"), but I needed raw image for processing, rather than compressed and wanted to choose the encoding) - I added input parameters to set the image width and height, as well as choosing the encoding.  It is available on [Github](https://github.com/japonophile/rosberrypi_cam "rosberrypi_cam").
- **ros\_dagu\_ctrl**: a little node to control the Dagu chassis, and send commands to the motors as well as to the camera pan/tilt servos.
- **ros\_sound**: a little node to play out a wav file.
- **ros\_trajectory\_analyzer**: the node running the main program: it commands the robot motors, uses OpenCV to analyse the image produced by the camera, and issues voice commands to the ros\_sound node, to say "Left" or "Right".

I will give more details on each node in another post.

**The result**

Here is what it looks like:

[![Dagu robot](https://img.youtube.com/vi/HUjCujzXGfI/0.jpg)](https://www.youtube.com/watch?v=HUjCujzXGfI "Dagu robot")

Note: if you listen carefully, you should hear the robot say "Left" and "Right" as it moves.

The image is analysed on the Mac using OpenCV.  Green lines show the direction of the points tracked from one frame to the next, thereby allowing to estimate the direction of the robot (blue line).  More on this later.

**Conclusion so far**

The Raspberry Pi is an exciting platform for robotic projects.

ROS seems very promising, as it offers a solid architecture for creating complex robotic applications.
