# Install and run Yolo V7 on Nvidia Jetson Nano
Make sure you are in MAXN Power Mode in order to compile in decent time.<br/>

## Environment <br/>

JetPack version: 4.5.1 <br/>
cuDnn: 8.0 <br/>
CUDA 10.2 <br/>
## Packages to install <br/>

PyTorch 1.8.0 and torchvision ([see link how to](https://forums.developer.nvidia.com/t/pytorch-for-jetson-version-1-11-now-available/72048)) <br/>
Example : For Python 3.6 Download and install torch-1.8.0-cp36-cp36m-linux_aarch64.whl <br/> <br/>
$ wget https://nvidia.box.com/shared/static/p57jwntv436lfrd78inwl7iml6p13fzh.whl -O torch-1.8.0-cp36-cp36m-linux_aarch64.whl<br/>
$ sudo apt-get install python3-pip libopenblas-base libopenmpi-dev libomp-dev<br/>
$ pip3 install Cython<br/>
$ pip3 install numpy torch-1.8.0-cp36-cp36m-linux_aarch64.whl<br/>
$ sudo apt-get install libjpeg-dev zlib1g-dev libpython3-dev libavcodec-dev libavformat-dev libswscale-dev <br/> 
$ git clone --branch v0.9.0 https://github.com/pytorch/vision torchvision   # see below for version of torchvision to download <br/><br/> 
Select the version of torchvision to download depending on the version of PyTorch that you have installed:<br/>
PyTorch v1.0 - torchvision v0.2.2<br/> 
PyTorch v1.1 - torchvision v0.3.0<br/> 
PyTorch v1.2 - torchvision v0.4.0<br/> 
PyTorch v1.3 - torchvision v0.4.2<br/> 
PyTorch v1.4 - torchvision v0.5.0<br/> 
PyTorch v1.5 - torchvision v0.6.0<br/> 
PyTorch v1.6 - torchvision v0.7.0<br/> 
PyTorch v1.7 - torchvision v0.8.1<br/> 
PyTorch v1.8 - torchvision v0.9.0<br/> 
PyTorch v1.9 - torchvision v0.10.0<br/> 
PyTorch v1.10 - torchvision v0.11.1<br/> <br/> 
$ cd torchvision <br/> 
$ export BUILD_VERSION=0.9.0  # where 0.x.0 is the torchvision version  <br/> 
$ python3 setup.py install --user <br/> 
$ cd ../  # attempting to load torchvision from build dir will result in import error <br/> 
$ pip3 install cython  <br/>
$ pip3 install -U 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI' <br/>
$ pip3 install pyyaml --upgrade <br/>
$ pip3 install --upgrade pip <br/>

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


