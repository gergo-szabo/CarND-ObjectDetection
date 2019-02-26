# Self-Driving Car Engineer Nanodegree


## Additional exercise: **Object detection** 

The goals / steps of this exercise are the following:
* Learn about MobileNets and separable depthwise convolutions.
* The SSD (Single Shot Detection) architecture used for object detection
* Use pretrained TensorFlow object detection inference models to detect objects
* Use different architectures and weigh the tradeoffs.
* Apply an object detection pipeline to a video.

Udacity project: [link](https://github.com/udacity/CarND-Object-Detection-Lab)

---

### Requirements

Install environment with [Anaconda](https://www.continuum.io/downloads):

```sh
conda env create -f environment.yml
```

Change TensorFlow pip installation from `tensorflow-gpu` to `tensorflow` if you don't have a GPU available.

### Resources

* TensorFlow object detection [model zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md)
  * ssd_mobilenet_v1_coco_11_06_2017 (~180 Mb)
  * rfcn_resnet101_coco_11_06_2017 (~720 Mb)
  * faster_rcnn_inception_resnet_v2_atrous_coco_11_06_2017 (~750 Mb)
* Driving video
* Fixed traffic cam video (https://www.youtube.com/watch?v=rpbkCUbWVio)

### Results

Output videos:
* [ssd_mobilenet_v1_coco_11_06_2017](model1.mp4)
* [rfcn_resnet101_coco_11_06_2017](model2.m4)
* [faster_rcnn_inception_resnet_v2_atrous_coco_11_06_2017](model3.mp4)

The object detection timing is depending on your hardware. The detection time roughly compares to each other:
```sh
ssd_mobilnet : rfcn_resnet101 : faster_rcnn_inception_resnet
80 ms : 320 ms : 1510 ms
```

It is hard to find a good KPI to describe the detection quality. Model performance in a few word:
* The ssd_mobilnet usually don't find multiple car on a frame. One car is not detected on the lawn. Detection is not continuous on every frame when a car moves. Cars are not detected in the distance.
* The rfcn_resnet101 finds almost every car at least once. Detection is not continuous on every frame when a car moves. Cars are detected in 
crossroad.
* The faster_rcnn_inception_resnet finds almost every car at least once. Sometimes it even detects cars which are partially covered. Detection is almost continuous. Cars are detected in the crossroad.
