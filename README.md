# RemoteSLAM

The main purpose of this repo is to provide the building blocks (software drivers, hardware and algorithms) for implementing SLAM systems using small and lightweight sensors (e.g., cameras, imu) .
We plan to improve this repo as we go, while receiving assistance from the community.
At this moment, the tool supports 3 types of monochrome cameras/sensors, combined with the Invense MPU 9X50 family:
* Matrix-Vision:  mvBlueFOX3-M/MLC 

    https://www.matrix-vision.com/USB3-vision-single-board-camera-mvbluefox3-m.html
* IDS-Imaging:  UI3271LE-M-GL   

    https://en.ids-imaging.com/store/ui-3271le-vu.html
* Arducam: (runs on Raspbian OS) to be added soon  
    
    https://www.arducam.com/products/camera-breakout-board/global-shutter-camera/



For the lense, a fisheye or wide FOV lense is highly recommended. All our calibrations are based mainly on Kalibr:  https://github.com/ethz-asl/kalibr .

Currently, the heavy lifting (SLAM algorithms) takes place on a remote host computer, receiving sensor data over wifi. This makes it easier to both test and develop different SLAM algorithms and new features.

SLAM algorithms supported:
* OrbSLAM3 (mono and mono+imu). 
   
    https://github.com/UZ-SLAMLab/ORB_SLAM3
    
    See on our Wiki page:  https://github.com/tau-adl/RemoteSLAM/wiki/Installing-and-running-OrbSLAM3-and-its-ROS-wrapper
* VINS-Fusion (mono+imu). 

    https://github.com/HKUST-Aerial-Robotics/VINS-Mono
    
    See on our Wiki page:  https://github.com/tau-adl/RemoteSLAM/wiki/Installing-and-running-Vins-Mono
    
SLAM algorithms soon to be supported:
* SVO (mono) .

  https://github.com/uzh-rpg/rpg_svo
  
* DSO and LDSO (mono). 

    https://github.com/JakobEngel/dso
    
    See on our Wiki page: https://github.com/tau-adl/RemoteSLAM/wiki/In-construction:--DSO-and-LDSO-(mono)-calibrations-and-ROS-wrappers


ROS wrappers (for real time implementations) are provided for both the sensors and the SLAM algorithms (where not available in the original repo) .


**Please find more information on the [wiki pages](https://github.com/tau-adl/RemoteSLAM/wiki) of this repository.**

**For questions or comments, please open an issue on Github.**


#
#
## (Short) Hardware and software overview

![PI_Case](https://github.com/tau-adl/RemoteSLAM/blob/main/PI_case_small.jpg)

A Raspberry Pi 4, running Ubuntu 18 and ROS Melodic, was chosen as the the edge computer for reading and transmitting the sensors' data over wifi. We'll make an effort to upload a PI image in the near future. As seen in the drawing above, an MPU 9x50 is attached to the rig in addition to the camera and PI. The assembly and the bracket can be found here: https://myhub.autodesk360.com/ue29b0f34/g/shares/SH919a0QTf3c32634dcfb5d81c4a5037ec4e ,  https://myhub.autodesk360.com/ue29b0f34/g/shares/SH919a0QTf3c32634dcfd4a362c701c7b391

An ubuntu 18 host computer receives the data from the PI, and runs the different SLAM algorithms. We (make our best effort to) provide all the links, relevant information and Ros wrappers needed for implementing and running the different SLAM algorithms in real time. 


  
