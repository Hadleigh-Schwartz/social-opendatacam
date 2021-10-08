# Getting started with CVAT 

[CVAT](https://github.com/openvinotoolkit/cvat) is an annotation tool for computer vision. Below is a guide for installing CVAT on your computer and using it to annotate video. 

### Installing CVAT
The videos linked below walk through installation of CVAT, based off of the steps detailed [here](https://github.com/openvinotoolkit/cvat). Installation instructions vary depending on your operating system, so make sure to choose the video corresponding to yours. 
<br>
<br>

* Mac: https://youtu.be/AVTxUXqtOoM
  - Docker Desktop for Mac can be found at https://docs.docker.com/desktop/mac/install/. 
* Ubuntu: https://youtu.be/bNhuOHtsv7M
* Windows: https://youtu.be/YRvhurhU1QU
  - Docker Desktop for Windows can be found at https://hub.docker.com/editions/community/docker-ce-desktop-windows.
  - Note that the steps in this video slightly diverge from the official instructions at https://github.com/openvinotoolkit/cvat. The official instructions appear to have some errors, so I recommend sticking to the video. 


### Annotating Video with CVAT - A Guided Example

Annotation entails labeling the objects in a video. Specifically, for each notable object in the video, you will draw a rectangle around it and then apply a label indicating its type. We will only be annotating people.

Annotation proceeds frame-by-frame. A video is comprised of many frames, and across frames, the positions and characteristcs of objects will change. To annotate these objects, we pause the video - stopping it at a specific frame - and annotate everything we see in this "still." As you will see in the demonstration, you only need to annotate certain <i>key frames </i>, and CVAT will fill in the blanks!

The steps below exaplin how to use CVAT to annotate videos on your computer (once you have installed it). It covers the following key concepts:
* Labeling objects with bounding boxes
* Tracking objects across frames 
* Selecting attributes for a label

Check out the video [here](https://youtu.be/vfM4XsVKdgQ) for a demonstration. 

1. Download Test-Task1.zip. Scroll up and click Test-Task1.zip. At the next page, click Download.
2. Open a terminal and enter the following commands, one by one. If you need you can refer back to the installation videos for instructions on how to open/use the terminal on your computer depending on its operating system.
  ```
  cd ~/cvat
  
  docker-compose up -d
  ``` 
2. Once you see the output shown below, open Google Chrome and go to localhost:8080. You should see the CVAT login page. 
![CVAT Ready](/cvat//assets/cvat-ready.png)
3. Log in with the credentials you created during installation. 
6. Click on "Tasks" in the menu bar. 
7. Click on "Import Task." Upload Test-Task1.zip, which you downloaded in Step 1. When it is finished importing, navigate to the task.
8. On the task page, you should see a pane titled "Jobs." Click on the job number of the first (and only) job. This should bring you to the annotation page.
  - Note the two available labels: "person" and "interaction." Note that an "interaction" can have one of the following <i>attributes</i>: "dancing," "fighting," or "walking together."       Such attributes describe the type of interaction. 
10. Start annotating! You can reference the official CVAT manual [here](https://openvinotoolkit.github.io/cvat/docs/manual/basics/track-mode-basics/). They detail how to annotate in "tracking mode," which is what we will be doing. Check out the video if you are still confused. 
11. When you're done, go back to your terminal and enter the command
 ```
  docker-compose down
  ```
  This shuts down the service, so it will no longer show up when you visit localhost:8080. 


