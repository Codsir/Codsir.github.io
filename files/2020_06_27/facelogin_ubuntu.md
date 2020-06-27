# 在Ubuntu上实现人脸识别登录

1. 安装Howdy: [howdy项目地址](<https://github.com/boltgolt/howdy>)

   ```python
   sudo add-apt-repository ppa:boltgolt/howdy
   sudo apt update
   sudo apt install howdy
   ```

2. 添加自己的face

   ```
   sudo howdy add
   ```

   报错：

   ```shell
   Enter a label for this new model [Initial model] (max 24 characters): tiger
   Camera path is not configured correctly, please edit the 'device_path' config value.
   Exception ignored in: <bound method VideoCapture.__del__ of <recorders.video_capture.VideoCapture object at 0x7f6bc5be02b0>>
   Traceback (most recent call last):
     File "/lib/security/howdy/recorders/video_capture.py", line 55, in __del__
       self.internal.release()
   AttributeError: 'VideoCapture' object has no attribute 'internal'
   
   ```

   解决方案:

   ```shell
   $ sudo apt-get install v4l-utils
   # 查看摄像头路径
   $ v4l2-ctl --list-devices
   USB 2.0 Camera: USB Camera (usb-0000:03:00.0-14):
   	/dev/video0
   $ sudo howdy config
   # 接下来更改config中的device_path = /dev/video0
   
   
   ```

   ```shell
   $ sudo howdy add
   Adding face model for the user tiger
   Enter a label for this new model [Initial model] (max 24 characters): tiger
   
   Please look straight into the camera
   Scan complete
   
   Added a new model to tiger
   ```

   3. 测试

      打开一个terminal

   ```shell
   $ sudo -i
   Identified face as tiger
   ```

   ```shell
   $ sudo howdy test
   
   Opening a window with a test feed
   
   Press ctrl+C in this terminal to quit
   Click on the image to enable or disable slow mode
   
   
   Closing window
   
   ```

   4. **屏幕锁屏后，enter进入输密码界面，程序就会识别出人，直接解锁**。

   5. 其它命令

      Usage:

      ```
      howdy [-U user] [-y] command [argument]
      ```

      | Command    | Description                                 |
      | ---------- | ------------------------------------------- |
      | `add`      | Add a new face model for an user            |
      | `clear`    | Remove all face models for an user          |
      | `config`   | Open the config file in your default editor |
      | `disable`  | Disable or enable howdy                     |
      | `list`     | List all saved face models for an user      |
      | `remove`   | Remove a specific model for an user         |
      | `snapshot` | Take a snapshot of your camera input        |
      | `test`     | Test the camera and recognition methods     |
      | `version`  | Print the current version number            |