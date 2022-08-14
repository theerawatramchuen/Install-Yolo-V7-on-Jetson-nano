# Install and run Yolo V7 on Nvidia Jetson Nano
Make sure you are in MAXN Power Mode in order to compile in decent time.<br/>

## Environment <br/>
Ubuntu 20.04 [get disk image](https://github.com/Qengineering/Jetson-Nano-Ubuntu-20-image)<br/>
JetPack version: 4.6 <br/>
cuDnn: 8.2 <br/>
CUDA 10.2 <br/>
## Verify Packages to install <br/>
'>>> import torch <br/>
'>>> import torchvision <br/>
'>>> print (torch.__ version__) <br/>
1.12.0 <br/>
'>>> print (torchvision.__ version__) <br/>
0.13.0 <br/>
'>>> exit() <br/>
$ python3 -m pip install cython  <br/>
$ python3 -m pip install -U 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI' <br/>
$ python3 -m pip install pyyaml --upgrade <br/>

## Clone the YOLOv7 repository<br/>
![alt text](https://github.com/WongKinYiu/yolov7/raw/main/figure/performance.png)<br/>
$ git clone https://github.com/WongKinYiu/yolov7.git <br/>
$ cd yolov7 <br/>
$ pip3 install -r requirements.txt <br/>

## Pre-trained Object Detection:

We have installed all of the modules. We now test the detection with pre-trained weights to confirm that all of our modules are working fine. You can use the mentioned command in terminal/cmd to detect objects with the pre-trained weights. <br/>

Note: YOLOv7 weights must need to be in the yolov7 folder, download the pre-trained weights file from this ([yolov7.py](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt)) or ([yolov7-tiny.py](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-tiny.pt)) if you want a higher processing speed such as video analytic project and move the downloaded file to the current working directory {yolov7} <br/>

$ python3 detect.py --weights yolov7.pt --source inference/images/horses.jpg --img 640 <br/><br/>
If everything is working fine, then you will be able to get results in the directory as mentioned below.<br/>
Results Directory : [yolov7/runs/detect/exp/horses.jpg] <br/>
![alt text](https://github.com/theerawatramchuen/Install-Yolo-V7-on-Jetson-Nano/blob/main/horses.jpg)<br/>


## Detect on Web Cam device 0
$ python3 detect.py --weights yolov7-tiny.pt --img 640 --source 0 <br/><br/>
![alt text](https://github.com/theerawatramchuen/Install-Yolo-V7-on-Jetson-Nano/blob/main/webcam_dev_0.jpg)<br/>


