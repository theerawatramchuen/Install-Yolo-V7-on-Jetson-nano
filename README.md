# Install and run Yolo V7 on Nvidia Jetson Nano
Hit the follow button on Medium to help increase reach of straight to the point guidance.<br/>

Make sure you are in MAXN Power Mode in order to compile in decent time.<br/>

## Environment <br/>

JetPack version: 4.5.1 <br/>
cuDnn: 8.0 <br/>
CUDA 10.2 <br/>
## Packages to install <br/>

PyTorch 1.8.0 ([see link how to](https://forums.developer.nvidia.com/t/pytorch-for-jetson-version-1-11-now-available/72048)) <br/>
Example : For Python 3.6 Download and install torch-1.8.0-cp36-cp36m-linux_aarch64.whl <br/> <br/>
pip3 install cython  <br/>
pip3 install -U 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI' <br/>
pip3 install pyyaml --upgrade <br/>

## Clone the YOLOv7 repository from the link.<br/>
git clone https://github.com/WongKinYiu/yolov7.git <br/>
cd yolov7 <br/>
pip install -r requirements.txt <br/>

