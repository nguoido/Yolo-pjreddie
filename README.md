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
