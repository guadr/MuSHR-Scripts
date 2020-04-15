# MuSHR-information

*First and foremost we want to site the MuSHR project for their support and donation of the bot*<br/><br/>

Srinivasa, S.S., Lancaster, P.E., Michalove, J., Schmittle, M., Summers, C., Rockett, M., Smith, J.R., Choudhury, S., Mavrogiannis, C.I., & Sadeghi, F. (2019). MuSHR: A Low-Cost, Open-Source Robotic Racecar for Education and Research. ArXiv, abs/1908.08031.

*We also would like to site yolo*<br/><br/>
Redmon, J., & Farhadi, A. (2018). YOLOv3: An Incremental Improvement. ArXiv, abs/1804.02767.

## Overviews
Our project was intended to create an autonomous vehicle with capabilities to move around on campus. Unfortunately, we ran into some issues due to the coronavirus that made it so we couldn't continue on to final steps with our process. But below we have outlined some of the steps we took on this project. On the robotics side, we needed to figure out how to do a few steps on our bot.

### Mapping
Due to the fact that the lidar that we had didn't work very well outside, we needed to figure out a way to map outdoors using camera input. To get this done, we used RTAB-Map. We had some computational constraints while using this as we had to make very small movements between frames or else it would lose localization. Through this technology, we were able to Map out our route on campus. 
![Mapped Out Campus Raw Image](https://https://github.com/guadr/MuSHR-information/images/raw_map.png)

We then cleaned our map manually, since our computational constraints limited our abilities to use loop closures.
![Mapped Out Campus Cleaned Image](https://https://github.com/guadr/MuSHR-information/images/cleaned_map.png)

This step was completely finished for our project.

### Object Detection
For object detection, we decided to use YoloV3 (You Only Look Once), as cited earlier. We choose yolov3 as it is extremely fast and pretty accurate. Due to our constrained environment, we needed to run something that didn't use too many resources. Yolov3 actually has a 'tiny' version that we were able to leverage that worked very well for us. 
![YoloV3 on Bot](https://https://github.com/guadr/MuSHR-information/images/YOLO_detection.jpg)

**Future steps**
1. create logic that uses this technology in order to be 'safe' on campus. Since it outputs the class that something is when it detects it, you could set boundaries on if its 80% sure its a person, then stop - or something of that nature.


### Autonomous Navigation
For basic autonomous navigation we leveraged the mushr nav stack that uses a particle filter for localization and a Receding Horizon Controller for path planning in order to operate the bot. This worked well for our indoor testing environment, which we were able to test it on before the coronavirus hit. 

**Future steps**
1. Deign a nav stack that works well for outdoor navigation within a constrained environment. This was our next step in the process before pivoting to web-design work due to the virus. 
