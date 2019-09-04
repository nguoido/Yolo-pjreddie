# Darknet #

* Nguồn: ```https://github.com/pjreddie/darknet ```    
* Để sử dụng các file có sẵn được train từ tập data ```COCO```      
	* https://github.com/pjreddie/darknet/blob/master/cfg/yolov3-tiny.cfg
	* https://pjreddie.com/media/files/yolov3-tiny.weights

* Với ảnh     
**Mất 1.4s** 
```
./darknet detect cfg/yolov3.cfg yolov3.weights data/dog.jpg
./darknet detector test cfg/coco.data yolo_coco/yolov3-tiny.cfg yolo_coco/yolov3-tiny.weights data/dog.jpg
```


* Với video      
**Chỉ đạt được 0.7-0.9 fps**    
```
./darknet detector demo cfg/coco.data yolo_coco/yolov3-tiny.cfg yolo_coco/yolov3-tiny.weights <video file>
```

# Test với Raspberry #

```
pi@raspberrypi:/working/ok/pjreddie $ ./darknet detector test cfg/coco.data yolo_coco/yolov3-tiny.cfg yolo_coco/yolov3-tiny.weights data/dog.jpg
layer     filters    size              input                output
    0 conv     16  3 x 3 / 1   416 x 416 x   3   ->   416 x 416 x  16  0.150 BFLOPs
....
Loading weights from yolo_coco/yolov3-tiny.weights...Done!
data/dog.jpg: Predicted in 35.553814 seconds.
Segmentation fault
```

Kiểm tra bằng câu lệnh sau:
```
pi@raspberrypi:/working/ok/pjreddie $ lscpu
Architecture:        armv7l
Byte Order:          Little Endian
CPU(s):              4
On-line CPU(s) list: 0-3
Thread(s) per core:  1
Core(s) per socket:  4
Socket(s):           1
Vendor ID:           ARM
Model:               4
Model name:          Cortex-A53
Stepping:            r0p4
CPU max MHz:         1200.0000
CPU min MHz:         600.0000
BogoMIPS:            38.40
Flags:               half thumb fastmult vfp edsp neon vfpv3 tls vfpv4 idiva idivt vfpd32 lpae evtstrm crc32
```
