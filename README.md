# Practical Assignment 3
**Deadline**: 02.04.2021

Please put your name(s) here:  
**Name:** Alex Tretyakov and Adnan Abu Ramadan
## Problem 3.1
### Ring Buffer (Points 30)
1. Fork the current repository
2. Study the new framework-code of
    - main.cpp
    - Camera Controller.h/cpp
    - Face.h/cpp
    - Marker.h/cpp
3. Check that the code is running correctly: it should show the video stream from the web-camera of your laptop.
4. Implement the _ring buffer_ from lecture by modifying the code in Camera Controller.cpp file (places marked with MODIFY CODE HERE tag)
5. In cases when producer overwrites a frame, which was not queried by consumer, report a _drop frame_ state by printing the corresponding message to console. Test it with increasing the delay time in `waitKey()`function in the main loop of consumer.

## Problem 3.2
### Face detection (Points 20)
Incorporate the face detection solution you done in the [Assignment 1](https://github.com/Jacobs-University/visir-tracker-01) into the framework in the following way:
1. Your face detector should return a vector of pointer to the `CFace` classes with detected faces: `std::vector<ptr_face_t> vpFaces`
2. Implement function `CMarker::markFaces()` and use it for drawing the faces to GUI
3. Perform face detection every 10th frame.

## Problem 3.3
### Face tracking (Points 50)
Incorporate the optical flow field solution you done in the [Assignment 2](https://github.com/Jacobs-University/visir-tracker-02) into the framework in the following way:
1. Your sparse optical flow should return a vector of 2-d points: `std::vector<Point2f>`
2. Implement function `CMarker::markVecOFF()` and use it for drawing the optical flow field (feel free to modify its arguments if needed).
3. Now detect the points only in the _face area_ , which is described in `vpFaces` variable.
4. Update the detected points every 10th frame (when face detection is used).
5. Track also the points added with mouse in the mouse callback function.
6. In between 10 frames (when the face detection is not applied) track the detected faces using the optical flow field. Update the position of faces in `vpFaces` variable variable for every frame.

## Problem 3.4
### Graphical User Interface (GUI) (Bonus Points 20)
1. Modify the function `CMarker::markGUI()` and design your own gui. Be creative!
2. Implement showing the current FPS in GUI

## Submission
Please submit the assignment by making a pull request.
**Important** : Please make sure that
- No _extra files_ are submitted (except those, which were mentioned in the assignment)
- The changes were made _only_ in those files where you were asked to write your code
- The Continuous Integration system (appVeyor) can build the submitted code
- The rendered images are also submitted in the folder "renders"
