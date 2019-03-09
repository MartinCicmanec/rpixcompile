# rpixcompile
Template for raspberry pi cross compilation of C/C++ code on Linux
# Installation

This project requires [raspberry tools](https://github.com/raspberrypi/tools).
The path to these tools has to be set in CMakeFiles.txt on the line:
```SET(tools /home/martin/git/tools) # tools is the repository folder of raspberry tools```  

# Compilation
```cmake . && make all```  