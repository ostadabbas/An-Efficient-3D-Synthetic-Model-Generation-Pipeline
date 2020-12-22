
<a href="https://web.northeastern.edu/ostadabbas/">
    <img src="https://web.northeastern.edu/ostadabbas/wp-content/uploads/2016/10/logo.png" alt="ACLAB logo" title="AC LAB" align="right" height="60" />
</a>

# Synthetic 3D Data Augmentation using Registration

:star: Star us on GitHub — it helps!
version 1.0.0 (Dec 2020)


This repository is an execution of the [white paper](https://web.northeastern.edu/ostadabbas/). This was a part of Masters thesis by [Kathan Vyas](vyas.k@northeastern.edu) and was developed with help and guidance within [Augmented Cognition Lab]((https://web.northeastern.edu/ostadabbas/).The given pipeline uses pointclouds scanned using any depth based camera (recomended: Intel Real Sense D435i) and implements two different variants of Iterative Closes Point based on availability of color infromation for the point clouds.  


## Table of content

- [Data collection Process](#data-collection-process)
    -[Hardware](#hardware)
    -[Setup](#Exraction-setup)
- [Installation](#Installation)
- [Usage](#Usage)
    - [Execution](#Execution)
- [Results](#Result)
    - [Output](#Output)
- [Post Processing](#Post-Processing)
- [License](#license)
- [Links](#links)
- [Contact](#Contact) 

## Data Collection Process

For the purpose of the project, we need to collect data for poinclouds or scans from a depth camera. The main algorithm accepts point clouds in wither .pcd or .ply format and it can accept any number of point clouds from 2 to 5000. The selection of number of point clouds is something that depends on requirement of the final registered point cloud's resolution.

### Hardware

In our experiments while creating the pipeline, we used [Intel Real Sense D435i] (https://www.intelrealsense.com/) which is a depth sensing camera from Intel. The Intel RealSense™ D4xx depth cameras can stream live depth (i.e. ranging data) and color data at up to 90 frames per second, and all the processing to generate the depth data is done on-board by the embedded D4 application-specific integrated circuits (ASIC). All the intel real sense cameras can be connected to the machine using an USB-C type cable and could be operated using dedicated [Real Sense SDK] (https://www.intelrealsense.com/sdk-2/). The sdk is only available for windows 10. The sdk can be used to capture a point cloud or record a sequence of point cloud with a file with extension ".bag". 

### Exraction-setup

The subject that is being scanned is to be kept in front of camera. You can use a rotating table on which you can put the subject and rotate it. You can then use teh real sense sdk -viewer API which is as shown in figure here.

**Image**

There are two ways the data collection can be done. 
1) Capture individual point clouds from various angles. You can select specific angles around the subject for instance capture a point cloud at every 60 degrees around the subject, so a total of 6 point clouds would cover 360 degrees around the body. If you plan to capture every 45 degrees, you will be able to capture 8 point clouds and so on. Please make sure you cover the subject from sides and angles. Please save the names of point clouds starting from 0. 

2) Record a "BAG" file which is nothing but a collection of continuously recorded point clouds. A "BAG" file can be recorded using the real sense sdk viewer app. You can record the file within a set frames per second. This FPS is important because later on when you extract frames from the "BAG" file, the number of frames extracted will be equal to fps*seconds_of_recorded_file . Once we have a "BAG" file, you can use the intel real sense api module [rs-convert] (https://github.com/IntelRealSense/librealsense/tree/master/tools/convert). The rs-convert is a console app for converting bag files to various formats (currently supported: PNG, RAW, CSV, PLY, BIN). In our case we can convert the frames to ply or pcd. The code to extract a  10 second "file.bag" which was recorded on 30fps will produce 300 frames using following code:

```
 cd path_to_ Intel RealSense SDK 2.0/tools

.\rs-convert.exe -l path_of_output_folder -i file.bag

```

Please save the point clouds starting from 0 to n point clouds. the structure of teh saved point clouds should be saved as:


```
folder
    -0.pcd
    -1.pcd
    .
    .
    .
    .
    -n.pcd
```

## Installation


## Usage

### Execution

## Result



## Contact: 
[Kathan Vyas](vyas.k@northeastern.edu)

[Sarah Ostadabbas](ostadabbas@ece.neu.edu)

## Installation

This document is for the latest Aimeos TYPO3 **20.10 release and later**.

- LTS release: 20.10 (TYPO3 9/10 LTS)
- Old LTS release: 19.10 (TYPO3 7/8/9 LTS)


## usage

## License

The Aimeos TYPO3 extension is licensed under the terms of the GPL Open Source
license and is available for free.

## Links

* [Web site](https://aimeos.org/integrations/typo3-shop-extension/)
* [Documentation](https://aimeos.org/docs/TYPO3)
* [Forum](https://aimeos.org/help/typo3-extension-f16/)
* [Issue tracker](https://github.com/aimeos/aimeos-typo3/issues)
* [Source code](https://github.com/aimeos/aimeos-typo3)
