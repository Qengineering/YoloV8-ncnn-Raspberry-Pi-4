# YoloV8 Raspberry Pi 4 or 5
![output image]( https://qengineering.eu/github/test_parkV8.webp )
## YoloV8 with the ncnn framework. <br/>
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/><br/>
For now: https://github.com/akashAD98/yolov8_in_depth<br>
Paper: on Ultralytics TODO list https://github.com/ultralytics/ultralytics<br/><br/>
Special made for a bare Raspberry Pi, see [Q-engineering deep learning examples](https://qengineering.eu/deep-learning-examples-on-raspberry-32-64-os.html)

------------

## Benchmark.
Numbers in **FPS** and reflect only the inference timing. Grabbing frames, post-processing and drawing are not taken into account.

| Model  | size | mAP | Jetson Nano | RPi 4 1950 | RPi 5 2900 | Rock 5 | RK3588<sup>1</sup><br>NPU | RK3566/68<sup>2</sup><br>NPU | Nano<br>TensorRT | Orin<br>TensorRT |
| ------------- | :-----:  | :-----:  | :-------------:  | :-------------: | :-----: | :-----: | :-------------:  | :-------------: | :-----: | :-----: |
| [NanoDet](https://github.com/Qengineering/NanoDet-ncnn-Raspberry-Pi-4) | 320x320 | 20.6  |  26.2 | 13.0 | 43.2  |36.0  |||||
| [NanoDet Plus](https://github.com/Qengineering/NanoDetPlus-ncnn-Raspberry-Pi-4) | 416x416 | 30.4  |  18.5  | 5.0  | 30.0  | 24.9  |||||
| [PP-PicoDet](https://github.com/Qengineering/PP-PicoDet-ncnn-Raspberry-Pi-4) | 320x320 | 27.0  |  24.0 | 7.5 | 53.7 | 46.7 |||||
| [YoloFastestV2](https://github.com/Qengineering/YoloFastestV2-ncnn-Raspberry-Pi-4) | 352x352 | 24.1 |  38.4 | 18.8 | 78.5 | 65.4 | ||||
| [YoloV2](https://github.com/Qengineering/YoloV2-ncnn-Raspberry-Pi-4) <sup>20</sup>| 416x416 | 19.2 |  10.1 | 3.0 | 24.0 | 20.0 | ||||
| [YoloV3](https://github.com/Qengineering/YoloV3-ncnn-Raspberry-Pi-4) <sup>20</sup>| 352x352 tiny | 16.6 | 17.7 | 4.4 | 18.1 | 15.0 | ||||
| [YoloV4](https://github.com/Qengineering/YoloV4-ncnn-Raspberry-Pi-4) | 416x416 tiny | 21.7 | 16.1 | 3.4 | 17.5 | 22.4 | ||||
| [YoloV4](https://github.com/Qengineering/YoloV4-ncnn-Raspberry-Pi-4) | 608x608 full | 45.3 | 1.3 | 0.2 | 1.82 | 1.5 | ||||
| [YoloV5](https://github.com/Qengineering/YoloV5-ncnn-Raspberry-Pi-4) | 640x640 nano | 22.5 | 5.0 | 1.6 | 13.6 | 12.5 | 58.8 | 14.8 | 19.0 | 100 |
| [YoloV5](https://github.com/Qengineering/YoloV5-ncnn-Raspberry-Pi-4) | 640x640 small | 22.5 | 5.0 | 1.6 | 6.3 | 12.5 | 37.7 | 11.7 | 9.25 | 100 |
| [YoloV6](https://github.com/Qengineering/YoloV6-ncnn-Raspberry-Pi-4) | 640x640 nano | 35.0 | 10.5 | 2.7 | 15.8 | 20.8 | 63.0 | 18.0 |||
| [YoloV7](https://github.com/Qengineering/YoloV5-ncnn-Raspberry-Pi-4) | 640x640 tiny | 38.7 | 8.5 | 2.1 | 14.4 | 17.9 |  53.4 | 16.1 | 15.0 ||
| [YoloV8](https://github.com/Qengineering/YoloV8-ncnn-Raspberry-Pi-4) | 640x640 nano | 37.3 | 14.5 | 3.1 | 20.0 | 16.3 | 53.1 | 18.2 |||
| [YoloV8](https://github.com/Qengineering/YoloV8-ncnn-Raspberry-Pi-4) | 640x640 small | 44.9 | 4.5 | 1.47 | 11.0 | 9.2 | 28.5 | 8.9 |||
| [YoloV9](https://github.com/Qengineering/YoloV9-ncnn-Raspberry-Pi-4) | 640x640 comp | 53.0 | 1.2 | 0.28 | 1.5 | 1.2 | |||| 
| [YoloX](https://github.com/Qengineering/YoloX-ncnn-Raspberry-Pi-4) | 416x416 nano | 25.8 | 22.6 | 7.0 | 38.6 | 28.5 | ||||
| [YoloX](https://github.com/Qengineering/YoloX-ncnn-Raspberry-Pi-4) | 416x416 tiny | 32.8 | 11.35 | 2.8 | 17.2 | 18.1 | ||||
| [YoloX](https://github.com/Qengineering/YoloX-ncnn-Raspberry-Pi-4) | 640x640 small | 40.5 | 3.65 | 0.9 | 4.5 | 7.5 | 30.0 | 10.0 |||

<b><sup>1</sup></b> The Rock 5 and Orange Pi5 have the RK3588 on board.<br>
<b><sup>2</sup></b> The Rock 3, Radxa Zero 3 and Orange Pi3B have the RK3566 on board.<br>
<b><sup>20</sup></b> Recognize 20 objects (VOC) instead of 80 (COCO)

------------

## Dependencies.
To run the application, you have to:
- A Raspberry Pi 4 or 5 with a 32 or 64-bit operating system. It can be the Raspberry 64-bit OS, or Ubuntu 18.04 / 20.04. [Install 64-bit OS](https://qengineering.eu/install-raspberry-64-os.html) <br/>
- The Tencent ncnn framework installed. [Install ncnn](https://qengineering.eu/install-ncnn-on-raspberry-pi-4.html) <br/>
- OpenCV 64-bit installed. [Install OpenCV 4.5](https://qengineering.eu/install-opencv-4.5-on-raspberry-64-os.html) <br/>
- Code::Blocks installed. (```$ sudo apt-get install codeblocks```)

------------

## Installing the app.
To extract and run the network in Code::Blocks <br/>
$ mkdir *MyDir* <br/>
$ cd *MyDir* <br/>
$ wget https://github.com/Qengineering/YoloV8-ncnn-Raspberry-Pi-4/archive/refs/heads/main.zip <br/>
$ unzip -j master.zip <br/>
Remove master.zip, LICENSE and README.md as they are no longer needed. <br/> 
$ rm master.zip <br/>
$ rm LICENSE <br/>
$ rm README.md <br/> <br/>
Your *MyDir* folder must now look like this: <br/> 
parking.jpg <br/>
busstop.jpg <br/>
YoloV8.cpb <br/>
yoloV8main.cpp <br/>
yoloV8.cpp <br/>
yoloV8.h <br/>
yolov8s.bin <br/>
yolov8s.param <br/>
yolov8n.bin <br/>
yolov8n.param <br/>

------------

## Running the app.
To run the application load the project file YoloV8.cbp in Code::Blocks. More info or<br/> 
if you want to connect a camera to the app, follow the instructions at [Hands-On](https://qengineering.eu/deep-learning-examples-on-raspberry-32-64-os.html#HandsOn).<br/>

------------

### Thanks.
A more than special thanks to [***FeiGeChuanShu***](https://github.com/FeiGeChuanShu/ncnn-android-yolov8), who adapted the YoloV8 model to the ncnn framework.<br><br>
![output image]( https://qengineering.eu/github/test_busV8.webp )

------------

[![paypal](https://qengineering.eu/images/TipJarSmall4.png)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=CPZTM5BB3FCYL) 


