# rpixcompile
Template for raspberry pi cross compilation of C/C++ code on Linux
# Installation

This project requires [raspberry tools](https://github.com/raspberrypi/tools).
The path to these tools has to be set in CMakeFiles.txt on the line:
```SET(tools /home/martin/git/tools) # tools is the repository folder of raspberry tools```  

# Compilation
```cmake . && make all```

# Future plans
Follow this [guide](https://medium.com/@amirmann/how-to-cross-compile-qt-for-raspberry-pi-3-on-linux-ubuntu-for-beginners-75acf2a078c)