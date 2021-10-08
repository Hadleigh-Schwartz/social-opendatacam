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


### Annotating with CVAT
Below is a step-by-step guide for using CVAT to annotate videos on your computer (once you have installed it). Check out the video here for a demonstration:

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
9. Start annotating! You can reference the official CVAT manual [here](https://openvinotoolkit.github.io/cvat/docs/manual/basics/track-mode-basics/). They detail how to annotate in "tracking mode," which is what we will be doing. Check out the video if you are still confused. 
10. When you're done, go back to your terminal and enter the command
 ```
  docker-compose down
  ```
  This shuts down the service, so it will no longer show up when you visit localhost:8080. 


