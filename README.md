# Person In/Out
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Person In/Out Detection algorithm based on the original [YOLOv5](https://github.com/ultralytics/YOLOv5).

## GUI Description
The algorithm uses YOLOv5 for person and door detection. 

To run the GUI app, follow the below instructions:
* Run the script,
```
python3 app.py
```
* Click the `start` button to open the view from the camera,
* Click the `detect door` button to run the main algorithm.
  

<p align="center">
  <img src="project_images/buttons.png" style='...'>
</p>

## Algorithm Description

The In/Out algorithm is implemented in a straightforward way. After a door is detected by `Door YOLO`, `Person YOLO` turns on and works until the window is closed.

*Note:* For getting the instructions on how to download the Door Detection model, go to the `models/README.md`.

When a person is located closer than a threshold distance from the door (called a threshold zone around the door), he is detected by YOLO. After the person disappears from the YOLO detector's sight, it takes the person’s bounding box from the last frame where the person was visible and computes the IoM (Intersection over Minimum) of the bounding box and the door. If the IoM is greater than a threshold, the output is - "Out", if it is smaller - "In". 

<p align="center">
  <img src="project_images/iom.png" style='...'>
</p>

## In/Out event Examples
<table style="width:100%">
  <tr>
    <th>Camera</th>
    <th>In/Out event</th>
    <th>Gif</th>
  </tr>
  <tr>
    <td>Cam. 1</td>
    <td>In</td>
    <td>
        <p align="center">
          <img src="project_images/in1.gif" style='...'>
        </p>
    </td>
  </tr>
  <tr>
    <td>Cam. 2</td>
    <td>Out</td>
    <td>
        <p align="center">
          <img src="project_images/out1.gif" style='...'>
        </p>
    </td>
  </tr>
  <tr>
    <td>Cam. 3</td>
    <td>In</td>
    <td>
        <p align="center">
          <img src="project_images/in2.gif" style='...'>
        </p>
    </td>
  </tr>
  <tr>
    <td>Cam. 4</td>
    <td>Out</td>
    <td>
        <p align="center">
          <img src="project_images/out2.gif" style='...'>
        </p>
    </td>
  </tr>
</table>

## How to use 
A quick guide on how to create an anaconda environment, download the dependencies and run the application:

<p align="center">
  <img src="project_images/demo.gif" style='...'>
</p>
