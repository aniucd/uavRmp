# uavRmp
Unmanned Aerial Vehicle R based Mission Planning


The [uavRmp](https://github.com/gisma/uavRmp) package is designed 
for uav autonomous mission planning. In the first place it is a simple and open source planning tool for monitoring flights of low budget drones based on ```R```. It provide an easy workflow for planning autonomous 
surveys including battery-dependent task splitting, save departures, and approaches of each monitoring chunks. It belongs to the ```uavR``` package family that provides more functionality for the pre- and post-processing as well as the analysis of the derived data.

## Supported UAV platforms

Up to now the ```uavRmp``` package has been dedicated to low budget rtf-UAVs (ready-to-fly) as the DJI Phantom series and Pixhawk based platforms as the 3DR Solo. However the future support will focus the Pixhawk based UAVs.

The majority of the open UAV community is using the PixHawk autopilot unit and for planning probably the [MissionPlanner](http://ardupilot.org/planner/) ground station software. Both are well documented and provide APIs (Application program interface) and easy to use GUIs (graphical user interface). Nevertheless it is has only a poor planning support for terrain following autonomous flights and no support for battery-dependent task splitting and save departures and approaches (MissionPlanner). Other ground station software solutions like the powerful [UgCS](https://www.ugcs.com/) is supporting custom DEM/DSM (in the commercial Pro license) but are still lacking an adequate capability for dealing with highly complex surfaces combined with low above surface flight altitudes and also does not provide task splitting according to the battery capacity.

The ```uavRmd``` bridges this gap  and  generates  ```MAVLINK``` format compliant mission files that can be uploaded to the Pixhawk controller using an integrated function or externally by any Ground Control Station software.


## Mission planning 

The core planning tool ```makeFP``` (make flight plan) creates either intermediate flight control files for the dji phantom x UAVs or ready to upload control files for the 3DR Solo. The dji control files are designed for using with the proprietary [Litchi](https://flylitchi.com/) flight control app exchange format, while the 3DR Solo files are using the ```MAVLINK``` common message format, that is used by the PixHawk flight controller family.

## The family

The package family will consist of 4 parts:

  * flight planning ```uavRmp```
  * forest analysis ```uavRfa```
  * remote sensing ```uavRrs```
  * archaeology ```uavRao```
  


The easiest way to obtain a fairly good runtime enviroment is to setup Linux as a dual boot system or in a VB. If interested in setting up a clean Xubuntu or Mint Linux you can use the  [postinstall script](http://giswerk.org/doku.php?do=export_code&id=tutorials:softgis:xubuntu:xubuntugis&codeblock=0setup) for installing most of the stuff. For using some of the the Solo related functions you need to install the [dronekit](http://python.dronekit.io/develop/installation.html) python libs in addition.

A full list of necessary libraries and binaries beyond ```R``` will soon be provided.


To install from ```github```  you need to have installed the ```devtools``` package.

```S
devtools::install_github("gisma/uavRmp", ref = "master")
```

If you want to install all dependencies use:

```S
devtools::install_github("gisma/uavRmp", ref = "master", dependencies = TRUE)
```
