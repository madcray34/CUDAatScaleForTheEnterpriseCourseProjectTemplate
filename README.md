# cannyEdgeDetectorNPP
Sample: cannyEdgeDetectorNPP
Minimum spec: SM 3.5

Key concepts:
Performance Strategies
Image Processing
NPP Library

## Project Description

This NPP CUDA Sample uses the NPP Canny edge detector to detect edges in gray scale images. 
By default, the input image is located in the "./data" directory, but you can specify a different path using the "-input" argument. 
Similarly, the output image is saved in the "./data" directory by default, 
but you can choose a different location using the "-out" argument. 
You can also adjust the low and high thresholds for the Canny edge detector using the "-ls" argument; 
the default values are 72 and 256, respectively.

The software supports gray scale images in any format that can be read by FREE_IMAGE_FORMAT, 
and it automatically saves output images in the same format as the input image.

If desired, you can take two additional steps to improve the performance of the software. 
First, you can add a Gaussian blur filter to the input image to reduce noise before applying the Canny edge detector. 
Second, you can modify the imageIO.h file to load color images using npp::loadImage(path, npp::ImageCPU_8u_C3).

Most of the result images suffer from noise, which confounds edge detection. 
However image "5.1.11" features minimal salt-and-pepper noise and well-defined border contours, enabling it to achieve superior edge detection performance.

To further improve the edge detector, we can develop interfaces that allow users to adjust the Canny edge detector's low and high thresholds, as well as the NORM parameter. 
This would enable users to fine-tune the detector's performance and achieve better results.

## Code Organization

```bin/```
contains the automatically built executable code, which is saved as a .exe file.

```data/```
contains input and output images used for the project. All images are in gray scale.

```lib/```
contains all the libraries used by the project. The Visual Studio 2019 IDE is set up to automatically load the includes and libraries from this folder relative to the .sln folder.

```src/```
contains the project's source code, which consists of a single file.

```README.md```
contains a description of the project.

```INSTALL```
provides a brief description of the requirements for the project.

```Makefile or CMAkeLists.txt or build.sh```
Tried to use CMake but the result is a little bit messy.

```run.sh```
is a script provided with the project that can be run after cloning the repository to generate all the outputs as loaded in the data folder.