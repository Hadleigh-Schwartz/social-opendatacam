# social-opendatacam

opendatacam is an open-source tool for quantifying the world. 

This repository contains code for a streamlined version of the original opendatacam. In this version, I have slightly modified the original code to intercept the output of the YOLO object detection and store it in a human-readable file. 

Users input a video (or a live camera stream) to opendatacam, and opendatacam runs an object detection machine learning model on this video to output <em> annotations </em> for the video. Annotations describe the objects that the model was able to detect and label. Each annotation corresponds to one object in one frame of the video, and includes 
<br>
(a) a class label for the object (e.g., person, car, bag, plant, etc.)
<br>
(b) bounding box coordinates specifying where in the frame the object is located
<br>
(c) a confidence score indicating the models confidence in its assignment of the label and bounding box. 

Below are some details on how to run the custom opendatacam set up and visualize results of its object detection, including a short tutorial.


### Visualizing annotations 
The python program visual_utils.py contains functions for visualizing annotations on whole videos and individual frames of videos. 

To generate an annotated video, enter this command in the terminal:
```
python3 visual_utils.py -i {PATH TO VIDEO} -a {PATH TO ANNOTATIONS} -f opendatacamyolo -o {DESIRED OUTPUT NAME} -v
```

Optionally, you can add -d to the end of the command in section x to generate a folder containing one image for each frame of the annotated video, as such:
```
python3 visual_utils.py -i {PATH TO VIDEO} -a {PATH TO ANNOTATIONS} -f opendatacamyolo -o {DESIRED OUTPUT NAME} -v -d
```

If you would only like to see annotations on one frame of the video:
```
python3 visual_utils.py -i {PATH TO VIDEO} -a {PATH TO ANNOTATIONS} -f opendatacamyolo -o {DESIRED OUTPUT NAME} -n {FRAME NUMBER}
```


### Example - Timesquare livestream 
In the sample-videos folder you will find four clips taken from a [livestream](https://www.youtube.com/watch?v=AdUw5RdyZxI) video of Times Square. Each video clip has a corresponding annotations file that was outputted from opendatacam, which can be found in the sample-annotations folder. 

Let's visually inspect the annotations for timesquare1.mp4. Enter the following command into the terminal:
```
python3 visual_utils.py -i sample-videos/timesquare1.mp4 -a sample-annotations/timesquare1-opendatacamyolo -f opendatacamyolo -o timesquare1-annotated -v
```
You should now see a file called timesquare1-annotated.mp4 in which all the objects the model detected are boxed in green, accompanied by a label and confidence score. It should look something like this: 
![Annotated timesquare1 screengrab](/assets/timesquare1-annotated.gif)

If you want to examine individual frames of the annotated video, run the command with the -d option, as such: 
```
python3 visual_utils.py -i sample-videos/timesquare1.mp4 -a sample-annotations/timesquare1-opendatacamyolo -f opendatacamyolo -o timesquare1-annotated -v -d 
```
You'll now see a folder named timesquare1-annotated in which you can find each annotated frame.
<br>
Lastly, to examine just one frame, enter the command
```
python3 visual_utils.py -i sample-videos/timesquare1.mp4 -a sample-annotations/timesquare1-opendatacamyolo -f opendatacamyolo -o timesquare1-annotated -n {FRAME NUMBER} 
```
For example, to see what the annotated 10th frame looks like, I'd enter 
```
python3 visual_utils.py -i sample-videos/timesquare1.mp4 -a sample-annotations/timesquare1-opendatacamyolo -f opendatacamyolo -o timesquare10th-annotated -n 10 
```
This gives us a file named timesquare10th-annotated.jpg that looks like this:
![Annotated 10th frame](/assets/timesquare10th-annotated.jpg)

 

