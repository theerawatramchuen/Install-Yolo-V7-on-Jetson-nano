# Install and run Yolo V7 on Nvidia Jetson Nano

![alt text](https://github.com/WongKinYiu/yolov7/raw/main/figure/performance.png)<br/>

## Environment <br/>
* Ubuntu 20.04 (Thanks for Q-Engineering team to prepare disk image to make this installation is super easy) [Click for disk image](https://github.com/Qengineering/Jetson-Nano-Ubuntu-20-image)<br/>
* MAXN Power Mode <br/>
* Packages Pre-installed <br/>
  * JetPack version: 4.6 <br/>
  * cuDnn: 8.2 <br/>
  * CUDA: 10.2 <br/>
  * pytorch: 1.12.0 <br/>
  * torchvision: 0.13.0 <br/>
  * opencv: 4.6 <br/>
## Packages to install <br/>
$ python3 -m pip install cython  <br/>
$ python3 -m pip install -U 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI' <br/>
$ python3 -m pip install pyyaml --upgrade <br/>
$ pip3 install numpy==1.19.4 <br/>

## Clone the YOLOv7 repository<br/>
$ git clone https://github.com/WongKinYiu/yolov7.git <br/>
$ cd yolov7 <br/>
$ pip3 install -r requirements.txt <br/>

## Pre-trained Object Detection:

If installation is good done for all modules. We are now ready for testing the detection with pre-trained weights to confirm that all of our modules are working fine. <br/>

Note: YOLOv7 weights must need to be in the yolov7 folder, download the pre-trained weights file from this ([yolov7.pt](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt)) or ([yolov7-tiny.pt](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-tiny.pt)) if you want a better FPS of video analytic then move the downloaded files to the current working directory yolov7 <br/>

$ python3 detect.py --weights yolov7.pt --source inference/images/horses.jpg --img 640 <br/><br/>
If everything is working fine, then you will be able to get results in the directory as mentioned below.<br/>
Results Directory : [yolov7/runs/detect/exp/horses.jpg] <br/>
![alt text](https://github.com/theerawatramchuen/Install-Yolo-V7-on-Jetson-Nano/blob/main/horses.jpg)<br/>


## Detect on Web Cam device 0
$ python3 detect.py --weights yolov7-tiny.pt --img 640 --source 0 ([short on youtube](https://youtube.com/shorts/BMCxzT6tjfc?feature=share))<br/><br/>
![alt text](https://github.com/theerawatramchuen/Install-Yolo-V7-on-Jetson-nano/blob/main/yolov7-webcam-jetson.jpg)<br/>


