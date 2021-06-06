# castevent
Python scripts which triggered by start/stop motion events in MotionEye feed a configured number of snapshots to a DeepstackAI object detection
server to analyse the images for a specified object (eg. person), and if found casts the camera stream to a google nest hub device/s.


1. Prerequisites:

  Python3
    Install Python3 and then the following python libraries:
    Imageio (https://imageio.readthedocs.io/en/stable/index.html)
    natsort (https://pypi.org/project/natsort/)
    catt - Cast All The Things (https://github.com/skorokithakis/catt)

  MotionEye (https://github.com/ccrisan/motioneye)
    Install and configure MotionEye and configure each of the cameras in your environment. 
    Enable video streaming on the cameras you wish to cast to a Nest Hub/s when a person/object is detected.
    Enable motion detection and set the options to your preferences.
    Under motion notifications enable "Run a command" and "Run an End Command" these are the scripts that will be run when a motion event starts
    and stops and where we trigger these castevent and stopevent scripts passing the event number (%v) and the "camname" which should be unique for
    each camera you have configured.
  
  Examples:
    Run a command: castevent %v frontdoor
    Run an end command: stopevent %v frontdoor
  
  Deepstack (https://docs.deepstack.cc/index.html#installation-guide-for-cpu-version)
    Install and configure Deepstack for object detection. If you have an NVidia GPU, highly recommend installing the GPU enabled version it will
    significantly reduce the detection times.


2. Installation

