bin檔只能放在 **/lib/firmware**

```
sudo insmod ap1302.ko fw="ap1302_ar1335_single_fw.bin"
```

http://yi-jyun.blogspot.com/2017/04/linux-kernel-firmware.html

https://blog.csdn.net/zifehng/article/details/60321966


---
# GStreamer

- 播放並顯示FPS
```
gst-launch-1.0 v4l2src ! videoconvert ! fpsdisplaysink video-sink=xvimagesink text-overlay=false sync=false -v 2>&1
```
- 只顯示FPS
```
gst-launch-1.0 v4l2src ! videoconvert ! fpsdisplaysink video-sink=fakesink text-overlay=false sync=false -v 2>&1
```

---
# IC2
## SFX
- write
```
sudo i2ctransfer -f -y 9 w4@0x3d 0x10 0x16 0x00 0x0F
```
- read
```
sudo i2ctransfer -f -y 9 w2@0x3d 0x10 0x16 r2
```
