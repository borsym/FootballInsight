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

| Model      | Epoch | Batch Size | Image Size | Precision | Recall | mAP50 | mAP50-95 | Ball Detection Rate |
| :---:  | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| M     | 25 | 16 | 400 |  0.510 |  0.470 |  0.515 |  0.288 | 0.11 |
| M     | 25 | 16 | 600 |  0.898 |  0.578 |  0.679 |  0.442 | 0.13 | 
| M     | 25 | 16 | 800 |  0.763 |  0.720 |  0.740 |  0.518 | 0.16 | 
| M     | 25 | 8 | 900 |  0.804 |  0.732 |  0.771 |  0.559 | 0.18 |
| M     | 25 | 8 | 1000|  0.865 |  0.759 |  0.806 |  0.591 | 0.23 |
| M     | 25 | 4 | 1400|  0.887 |  0.823 |  0.866 |  0.638 | 0.40 |
| M     | 125 | 4 | 1400|  0.944 |  0.828 |  0.872 |  0.665 | 0.42 |

#### YOLOv7:


#### YOLOv5:
---

## 2. Object Detection + Object Tracking

### No training:

### Custom training:
