# social-opendatacam

opendatacam is an open-source tool for quantifying the world. 

This repository contains code for a streamlined version of the original opendatacam. In this version, I have slightly modified the original code to intercept the output of the YOLO object detection and store it in a human-readable file. 

Users input a video (or a live camera stream) to opendatacam, and opendatacam runs an object detection machine learning model on this video to output <em> annotations </em> for the video. Annotations describe the objects that the model was able to detect and label. Each annotations corresponds to one object in one frame of the video, and includes (a) a class label for the object (e.g., person, car, bag, plant, etc.), (b) bounding box coordinates specifying where in the frame the object is located, (c) a confidence score indicating the models confidence in its assignment of the label and bounding box. 

Below are some details on how to run the custom opendatacam set up and visualize results of its object detection, including a short tutorial.


### Visualizing annotations 

Visualizing annotations on an individual frame of a video or a whole video is accomplished with the python program visual_utils.py. 

To generate an annotated video, enter this command in the terminal:
python3 visual_utils.py -i {VIDEO FILENAME} -a {ANNOTATIONS FILENAME} -f opendatacamyolo -o {DESIRED OUTPUT NAME} -v

Optionally, you can add -d to the end of the command in section x to generate a folder containing one image for each frame of the annotated video, as such:
python3 visual_utils.py -i {VIDEO FILENAME} -a {ANNOTATIONS FILENAME} -f opendatacamyolo -o {DESIRED OUTPUT NAME} -v -d


If you would only like to see annotations on one frame of the video:
python3 visual_utils.py -i {VIDEO FILENAME} -a {ANNOTATIONS FILENAME} -f opendatacamyolo -o {DESIRED OUTPUT NAME} -n {FRAME NUMBER}

In all cases, make sure to put both video and annotations file in the same folder as visual_utils.py



Example - Visualizing annotations on a timesquare livestream


 

