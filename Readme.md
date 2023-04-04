# **Football Insights**

### Computer vision based system to track the flow of football matches and create player-specific summaries. 

## Demo

![Result](resources/gifs/end.gif)

---

## Computer Vision Tasks Used:

- **Object Detection**: YOLO
- **Object Tracking**: ByteTrack, Deepsort
- **Optical Flow**: UniMatch
- **Pose Estimation**: Metrabs

## Dataset:

The [Dataset](https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc/dataset/4) used is from **Roboflow**. It contains 255 images: 204 train, 38 validation, 13 test. 

![Demo Image](resources/images/demo.png)

### Downloading the Dataset:

```python 
!pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="YOUR_KEY")
project = rf.workspace("roboflow-jvuqo").project("football-players-detection-3zvbc")
dataset = project.version(4).download("DATASET_TYPE")
```

# **Results:**

## 1. Object Detection:

### No Training:
#### YOLOv8:


#### YOLOv7:


#### YOLOv5:
---
### Custom Training:

#### YOLOv8:


#### YOLOv7:


#### YOLOv5:
---

## 2. Object Detection + Object Tracking

### No training:

### Custom training:
