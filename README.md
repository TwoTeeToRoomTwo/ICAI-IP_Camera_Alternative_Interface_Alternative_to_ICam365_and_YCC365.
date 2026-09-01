![alt text](https://raw.githubusercontent.com/TwoTeeToRoomTwo/-ICAI---IP-Camera-Alternative-Interface.-Alternative-to-ICam365-YCC365/refs/heads/main/ICAI3.png)

**NB!!!**

**1.** Before using the app **ICAI**, let's tnx to [Jalecom](https://github.com/Jalecom/AJ_HC1703L_Teardown) for providing the tools to "bypass" the imposed restrictions.

**2.** ONLY AFTER you successfully apply the [Jalecom's Hack](https://github.com/Jalecom/AJ_HC1703L_Teardown), you can come back here again and try with using the [ICAI app](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365.).

**3.** If you have made changes to the file: [debug_cmd.sh](https://github.com/Jalecom/AJ_HC1703L_Teardown/blob/main/sdcard/debug_cmd.sh) and you have removed the account and password with the lines:

`
...#
mount --bind /mnt/hack/group /etc/group
mount --bind /mnt/hack/passwd /etc/passwd
mount --bind /mnt/hack/shadow /etc/shadow
#...
`

than, you also need to change the information in: `FTP_USER=` and `FTP_PASSWORD=` under the `class RecordingsBrowser(tk.Toplevel):` of the file: [recordings_browser.py](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/recordings_browser.py) with yours credential! Also you must to change the specified directory in the file: [IP_Camera.desktop](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/IP_Camera.desktop) to make the icon visible and replace the information inside [camera_config.json](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/camera_config.json) with your IP addresses!!!!

**4.** To use the file manager with the button: **"VIEW RECORDS"**, you need to edit the line in the file [config.txt](https://github.com/Jalecom/AJ_HC1703L_Teardown/blob/main/SDCARD_v0.4/config.txt) where the type of [hack](https://github.com/Jalecom/AJ_HC1703L_Teardown/tree/main/SDCARD_v0.4) is set. It should look like this: `HACKTYPE=T`. The file [config.txt](https://github.com/Jalecom/AJ_HC1703L_Teardown/blob/main/SDCARD_v0.4/config.txt), which you downloaded from the [Jalecom's](https://github.com/Jalecom/AJ_HC1703L_Teardown) repo along with the other files and folders, is located on your "SD card" and by default looks like this: `HACKTYPE=SD`. This is the only way to unlock the ability to record video on your camera's memory card! If you leave the `HACKTYPE=SD`, the file browser window will still open, but if there are no folders or files whose names contain the date and time, you will not see anything!

**5.** IM TOO LAZY, TO TRANSLATE, ALL OF THE TEXT, OF THE EXPLANATIONS. SO GOOD LUCK WITH THAT TASK 

**6.** The app is far from complete! You are welcome to use your brain and help with it!

**7.** [tracking_module.py](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./blob/main/tracking_module.py) is not usable for now, because when the camera's built-in object tracking feature is **"ON"** in your factory application(**ICam365,Ycc365**..), there is a conflict with YOLO's PTZ commands and the camera's built-in "tflate" model! So, you already know that, **ICAI** is made to use the **"YOLO"** models, at an early stage, and it was doing its job very well. So I got hung up with the "conflict" issue. The model is located in the [YOLOv12](https://github.com/TwoTeeToRoomTwo/ICAI-IP_Camera_Alternative_Interface_Alternative_to_ICam365_and_YCC365./tree/main/YOLOv12) folder. At a later stage, if I think of something I will make it working again! 

I hope, the app, will be useful to someone. I'm not a programmer, I relied on the help of my local AI ​​model, and therefore gross errors are possible, so I apologize in advance!
NJOY!!!

For a while, to forget. DO NOT DELETE THE FOLDER "talking"! The folder is important for the app to work properly, it serves in that way: When we press and hold the "Intercom" button, an audio file is created in the "talking" folder, then the file is sent to the camera's memory, and then the audio file is played through the built-in speaker of your camera. After the playback of the audio file is finished, it is deleted automatically, both from the "talking" folder and from the device's memory. For this reason, the folder always appears to be empty!
