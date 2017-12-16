# Fruit Detection and Yield Estimation Based on Yolo v2
## Introduction
The objective is to identify individual apples in the images and estimate the total number of apples over the dataset by accumulating the counts. Detection newwork and source code are based on Yolo v2 model.

This project is supported by NYU Robotic Design Team.

Weights file available at

https://drive.google.com/open?id=1Tpl_IscaV1Ybd6pc3vJQ38mDZVMszD_o 

## Dataset
ACFR Orchard Fruit Dataset, released by Australian Centre for Field Robotics, The University of Sydney

http://data.acfr.usyd.edu.au/ag/treecrops/2016-multifruit/

The corrsponding data used in this project is storage in /data/apple
         
## Development and Test Environment

Ubuntu 16.04, Cuda 9.1

GTX 1080 Ti, i9-7900X

## Instruction
### Data Format Converting
/python/
### Training
./darknet detector train cfg/[data file] cfg[cfg file] [model file]

Example:
./darknet detector train cfg/apple.data cfg/yolo-apple2.cfg darknet19_448.conv.23
### Detection Single Image
./darknet detect cfg/[cfg file] [weights file] data/[filename] -thresh [threshold]

Example:
./darknet detect cfg/yolo.cfg yolo.weights data/test.png -thresh 0.05
Results are saved in /predictions
### Detection Multiple Image
Change the path for the txt file containing image list for test in /examples/detector.c Line 662

Start by running

./darknet detect cfg/[cfg file] [weights file] -thresh [threshold]

Example:

./darknet detect cfg/yolo.cfg yolo.weights -thresh 0.05

Results are saved in /predictions

## References
[1] ACFR Orchard Fruit Dataset, the Australian Centre for Field Robotics, The University of Sydney, Australia, 2016, http://data.acfr.usyd.edu.au/ag/treecrops/2016-multifruit/

[2] S. Bargoti and J. Underwood, "Deep fruit detection in orchards," 2017 IEEE International Conference on Robotics and Automation (ICRA), Singapore, 2017, pp. 3626-3633.

[3] Bargoti, S. and Underwood, J. P. (2017), Image Segmentation for Fruit Detection and Yield Estimation in Apple Orchards. J. Field Robotics, 34: 1039–1060. 

[4] McCool, C.; Sa, I.; Dayoub, F.; Lehnert, C.; Perez, T.; Upcroft, B. Visual Detection of Occluded Crop: For automated harvesting. In Proceedings of the International Conference on Robotics and Automation, Stockholm, Sweden, 16–21 May 2016.

[5] Joseph Redmon, Santosh Divvala, Ross Girshick, Ali Farhadi, “You Only Look Once: Unified, Real-Time Object Detection,” the IEEE Conference on Computer Vision and Pattern Recognition (CVPR), Las Vegas, 2016, pp. 779-788.

For more information and instruction about Yolo v2:

https://pjreddie.com/darknet/yolo/

