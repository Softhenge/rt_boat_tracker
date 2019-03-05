# rt_boat_tracker
Real Time Boat Tracker

## Description

The tool detects and tracks special boats from live video or video file.

## Detection and tracking techniques

The project is based on a yolo object detection model. A yolo model has been trained which detects special boats.

The tracking algorithm uses the trained model to detect boats on each video frame. 
Then it compares detections with the detections founded in previous frame and compares the relative locations of the objects considering objects as the same if they are near to each other.

## Dependencies

- Yolo v3
- OpenCV

## How to build and run

1. Clone [Windows and Linux version of Darknet Yolo v3](https://github.com/AlexeyAB/darknet#how-to-train-to-detect-your-custom-objects) and build with GPU support.
2. Locate your boat detection model in the `build\darknet\x64\backup` directory and the yolo `.cfg` file in `build\darknet` directory.
3. Clone `rt_boat_tracker` inside the `build\darknet` directory, open `build\darknet\yolo_console_dll.sln` in MSVS2015 and replace the `yolo_v2_class.hpp` and `yolo_console_dll.cpp` files with the rt_boat_tracker checkouted files.
4. Build the project.
5. Run the `.exe` file `build\darknet\x64\yolo_console_dll.exe` and enter video file name.

