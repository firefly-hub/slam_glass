# Real-time indoor SLAM with glass detection
This code is a modified version of glam code (v39).
We add a glass detection algorithm and integrated it with the existing SLAM algorithm to produce maps with detected glass panels marked as solid wall objects. We developed and tested our algorithm and code on an unmodified PR2 robot platform.

## Compile source code
Clone the repository in a working catkin workspace.
run ```./configure``` under ```gmapping_glass/gmapping_export``` directory, then do ```cd ..;make -f Makefile.gmapping```.
After the libraries is compiled, go back to catkin root directory and compile the application with ```catkin_make```.

## Launch slam_glass service
```
roslaunch slam_glass slam_glass_pr2.launch
```

## Test dataset
You can download our test dataset [here](http://experimentdata.themagiclab.org/static/slam_glass_test_dataset.tar.gz) and run it against slam_glass service node. Simply extract the bag files from the compressed file and use ```rosplay``` to playback the data files. You should hopefully produce a map similar to the following figure.

<img src="https://cloud.githubusercontent.com/assets/6646691/10475396/f3016798-728e-11e5-9904-7eca19055e98.png" width="200">

**Figure 1. SLAM with glass detection.**

If the same dataset is run against the default SLAM ROS package, the generated map will be similar to Figure 2.

<img src="https://cloud.githubusercontent.com/assets/6646691/10475464/a62dc208-728f-11e5-902d-4d0dd8d1c263.png" width="200">

**Figure 2. Default SLAM without glass detection.**
