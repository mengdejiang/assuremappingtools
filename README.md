![Assure logo](https://user-images.githubusercontent.com/20182801/61394821-fb224f00-a8fe-11e9-82d5-6e008df6710e.png)
![banner](https://user-images.githubusercontent.com/20182801/61394945-3e7cbd80-a8ff-11e9-8930-f827ef2cfd69.png)
# ASSURE mapping tools
Desktop based tool for viewing, editing and saving road network maps for autonomous vehicle platforms such as Autoware.

### * News: V0.5 build for Ubuntu 18.04 is now available in separate [branch](https://github.com/hatem-darweesh/assuremappingtools/tree/ubuntu18.04_build). 

### Operating System

- Ubuntu 16.04
- Ununtu 18.04 
  [Fast fix](https://github.com/hatem-darweesh/assuremappingtools/wiki), or 
  [Custom build branch](https://github.com/hatem-darweesh/assuremappingtools/tree/ubuntu18.04_build)

### Prerequisites libraries: 
- For Ubuntu 16.04: (master branch)
1. Install [OpenCV 2.4](https://docs.opencv.org/2.4/doc/tutorials/introduction/linux_install/linux_install.html)
    don't forget to checkout ver 2.4.13.7, default git clone download ver 4.0
2. Install ROS [kinetic](http://wiki.ros.org/kinetic/Installation/Ubuntu)
3. Install libtinyxml, freeglut3, libglew, libpcl1.7, libpugixml-dev, libgeographic
4. Install ros-kinetic-pcl-ros

- [For Ubuntu 18.04](https://github.com/hatem-darweesh/assuremappingtools/tree/ubuntu18.04_build)
1. Install [OpenCV 2.4](https://docs.opencv.org/2.4/doc/tutorials/introduction/linux_install/linux_install.html)
    don't forget to checkout ver 2.4.13.7, default git clone download ver 4.0
2. Install ROS [melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)
3. Install libtinyxml, freeglut3, libglew, libpcl1, libpugixml-dev, libgeographic, libplib, libglm
4. Install ros-melodic-pcl-ros

- Library link issue:
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:libs 

### GPU acceleration 
- The editor works faster with GPU accelerator specially for large maps

### Supported Roadnetwork Map formates (Load)
- [OpenPlanner](https://gitlab.com/autowarefoundation/autoware.ai/core_planning) map format .kml 
- Signle path file .csv 
- Vector Map, collection of .csv files composing the map
- [OpenDRIVE](http://www.opendrive.org/), is open file format for the logical description of road networks .xodr
- [Lanelet2](https://github.com/fzi-forschungszentrum-informatik/Lanelet2), map format .osm, with autoware extention

### Supported Roadnetwork Map formates (Save)
- [OpenPlanner](https://gitlab.com/autowarefoundation/autoware.ai/core_planning) map format .kml 
- Google Earth .kml format, if only the loaded vector map has GPS information.
- [Lanelet2](https://github.com/fzi-forschungszentrum-informatik/Lanelet2), map format .osm

### Supported Pointcloud data
- pointcloud map .pcd files
- rosbag of (LIDAR, Camera, Pose) .bag files _comming soon_

### Supported Map Semantics
- Lanes
- Waypoints
- Road lines
- Traffic Lights
- Stop Lines
- Traffic Sign 
- Road Boundaries
- Crossings 

### Tutorials
- [Video Tutorials V0.5](https://youtu.be/lignj-gVGVg)
- [Video Tutorials V0.2](https://youtu.be/PXcE7XMSKck)
- [Older Video Tutorials](https://www.youtube.com/watch?v=p_4HwJvu084&list=PLVAImlqqGbr4G8GXMsqp6dMhbKxTCEnrh&index=1)

## New features
- Saving lanelet2 using either UTM from original lanelet library or MGRS from the autoware extention. 
- ASSURE map editor save the projection data with the .kml and .osm files to be use when the map is loaded. 
- Accurate conversion from vector map to lanelet2 is available. use should find the projection string for the ptoj library online. 
- This [website](https://spatialreference.org/ref/epsg/2449/) provides prepared projection string, if you select [Proj4js format](https://spatialreference.org/ref/epsg/2449/proj4js/). you will get this string which represent central Japan area.

### Known Issues
- No support for multi-storey parking maps yet.
- Exporting traffic lights and signs to lanelet2 require connection all Ids correctly between light-lane-stopline. 
