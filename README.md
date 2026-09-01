![alt text](https://raw.githubusercontent.com/TwoTeeToRoomTwo/-ICAI---IP-Camera-Alternative-Interface.-Alternative-to-ICam365-YCC365/refs/heads/main/ICAI3.png)

With ❤️ from 🇧🇬

### **_!!!NB!!!_**

--------------------------------------------------------------------------------------------------------------

- **1.** Before using the app **ICAI**, let's tnx to [Jalecom](https://github.com/Jalecom/AJ_HC1703L_Teardown) for providing the tools to "bypass" the imposed restrictions.

- **2.** **ONLY AFTER you successfully apply the [Jalecom's Hack](https://github.com/Jalecom/AJ_HC1703L_Teardown), you can come back here again and try with using the [ICAI](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365.) app!!!**



### **Let's install the dependencies**

--------------------------------------------------------------------------------------------------------------

**_It is preferable to create a virtual environment:_**

```sh
python -m venv .venv
```

Then, to activate it:

```sh
source .venv/bin/activate
```

Than, install the requirements, from the file:

```sh
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

If you are using Arch and don't care about virtual environments:

```sh
sudo pacman -Syu \
  opencv \
  python-pygame \
  python-requests \
  python-numpy \
  python-psutil \
  python-scipy \
  python-sounddevice \
  python-tk
```

_If you have a problem with **ultralytics** you will need to use a virtual environment anyway! So we go back to the beginning of that chapter!!_



### **Let's prepare the settings and change some things before we start!**

--------------------------------------------------------------------------------------------------------------

- **1.** You must to change the specified directory in the file: [IP_Camera.desktop](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/IP_Camera.desktop) to make the icon visible and replace the information inside.

In this way:

```desktop
[Desktop Entry]
Comment=Start IP_CAMERA
Exec=/bin/bash -c 'cd "$(dirname "%k")" && python WORKABLE.py'
Icon=/YOUR_PATH_TO/ICAI/icon/cctv.png
Name=IP_Camera
StartupNotify=true
Terminal=false
Type=Application
Version=1.0
```

- **2.** Change the 

```json

"ip": "CAMERA_IP",
"name": "THE_NAME_OF_THE_CAMERAS",
"rtsp_url": "rtsp://CAMERA_IP:554/0/av0",
"audio_url": "rtsp://CAMERA_IP:8001/0/audio",

```
inside [camera_config.json](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/camera_config.json) with your real data!!!!

- **3.** To use the file manager with the button: **"VIEW RECORDS"**, you need to edit the line in the file [config.txt](https://github.com/Jalecom/AJ_HC1703L_Teardown/blob/main/SDCARD_v0.4/config.txt) where the type of [hack](https://github.com/Jalecom/AJ_HC1703L_Teardown/tree/main/SDCARD_v0.4) is set. It should look like this: `HACKTYPE=T`. The file [config.txt](https://github.com/Jalecom/AJ_HC1703L_Teardown/blob/main/SDCARD_v0.4/config.txt), which you downloaded from the [Jalecom's](https://github.com/Jalecom/AJ_HC1703L_Teardown) repo along with the other files and folders, is located on your "SD card" and by default looks like this: `HACKTYPE=SD`. This is the only way to unlock the ability to record video on your camera's memory card, through the option that you must have already enabled from your factory application **ICam365/Ycc365**! If you leave the `HACKTYPE=SD`, the file browser window will still open, and you will be able to play, delete or copy the files, but if there are no folders or files whose names contain the date and time (as default), you will not see anything!


- **4.** [tracking_module.py](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/tracking_module.py) is not usable for now, because when the camera's built-in object tracking feature is turned **ON** in your factory application(**ICam365,Ycc365**..), there is a conflict with YOLO's PTZ commands and the camera's built-in "tflate" model! So, you already know that, **ICAI** is made to use the **"YOLO"** models, at an early stage, and it was doing its job very well. So I got hung up with the "conflict" issue. The model is located in the [YOLOv12](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./tree/main/YOLOv12) folder. At a later stage, if I think of something I will make it working again! 

- **5.** _IM TOO LAZY, TO TRANSLATE, ALL OF THE TEXT, OF THE EXPLANATIONS. SO GOOD LUCK WITH THAT TASK_


**_Start the app_**
--------------------------------------------------------------------------------------------------------------

If you have created a virtual environment as instructed above, еdit the `Exec=` line in the file [IP_Camera.desktop](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/IP_Camera.desktop)

```desktop
[Desktop Entry]
Comment=Start IP_CAMERA
Exec=/bin/bash -c 'cd "$(dirname "%k")" && python WORKABLE.py'
Icon=/YOUR_PATH_TO/ICAI/icon/cctv.png
Name=IP_Camera
StartupNotify=true
Terminal=true
Type=Application
Version=1.0
```
to look like this:

```desktop
[Desktop Entry]
Comment=Start IP_CAMERA
Exec=/bin/bash -c 'cd "$(dirname "%k")" && source .venv/bin/activate && python WORKABLE.py'
Icon=/YOUR_PATH_TO/ICAI/icon/cctv.png
Name=IP_Camera
StartupNotify=true
Terminal=false
Type=Application
Version=1.0
```

If you didn't created a virtual environment..... Then, you have nothing to worry about 😸 and you can start the app from the "IP_Camera.desktop" like a normal or, you can run it directly through the terminal with: 

```sh
python WORKING.py
```

And with virtual env:

```sh
source .venv/bin/activate
python WORKING.py
```

GOOD LUCK!

The app is far from complete! You are welcome to use your brain and help with it!

_I hope, the app, will be useful to someone. I'm not a programmer, I relied on the help of my local AI ​​model, and therefore gross errors are possible, so I apologize in advance!
NJOY!!!_

For a while, to forget. DO NOT DELETE THE FOLDER "talking"! The folder is important for the app to work properly, it serves in that way: When we press and hold the "Intercom" button, an audio file is created in the "talking" folder, then the file is sent to the camera's memory, and then the audio file is played through the built-in speaker of your camera. After the playback of the audio file is finished, it is deleted automatically, both from the "talking" folder and from the device's memory. For this reason, the folder always appears to be empty!

With ❤️ from 🇧🇬
