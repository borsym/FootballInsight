### Research the most recent methods in object detection, tracking and optical flow

Object detection is a computer vision technique that works to identify and locate objects within an image or video. Specifically, object detection draws bounding boxes around these detected objects, which allow us to locate where said objects are in (or how they move through) a given scene:
Yolov5,v7,v8, faster R-CNN

Object tracking refers to the ability to estimate or predict the position of a target object in each consecutive frame in a video once the initial position of the target object is defined. This is a very useful technique in many applications, such as video surveillance, traffic monitoring, and robotics
DeepSORT, ByteTrack

YOLO and ByteTrack can work together in different ways depending on the specific application and implementation. However, here is a general overview of how YOLO and ByteTrack can work together in an object detection and tracking system:

Object detection with YOLO: The first step is to use YOLO to detect objects in the input video or image. YOLO processes the entire image in one forward pass of a neural network and outputs a list of detected objects with their class labels and bounding boxes.

Object tracking with ByteTrack: Once the objects are detected, ByteTrack takes over to track the objects across frames. ByteTrack uses a motion model to predict the next location of each object based on its previous position and velocity. Then, it searches for the object in the predicted location within a search region in the next frame. If the object is found, ByteTrack updates its position and velocity, otherwise, it considers the object as lost.

Integration of YOLO and ByteTrack: YOLO and ByteTrack can be integrated by using the YOLO detections to initialize object tracks in ByteTrack or by updating the object state in ByteTrack with the new YOLO detections that occur in subsequent frames. By doing this, ByteTrack can leverage the object detection capabilities of YOLO to improve the robustness and accuracy of the tracking system.

Object classification and re-identification: Depending on the application, the system can include additional modules to perform object classification or re-identification. For example, a re-identification module can match the tracked objects with their identities in a database or in previous frames, allowing the system to track individual objects over long periods of time.

Overall, by combining the object detection capabilities of YOLO with the object tracking capabilities of ByteTrack, we can create a robust and accurate system for real-time object detection and tracking in various scenarios.

optical flow
Optical flow is a computer vision technique used to estimate the motion of objects in an image or video sequence. It works by analyzing the apparent motion of pixels in consecutive frames of a video, and computing the displacement or flow of each pixel from one frame to the next. Optical flow can be used to estimate both the magnitude and direction of motion, as well as the velocity of objects in the scene.

Computer vision with Object deteciton:
https://www.youtube.com/watch?v=ArPaAX_PhIs&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=1
How to detect edges?
we have a 6x6x1 image and a filter/kernel
vetrical edge detection:
[[-1,0,1],
[-1,0,1],
[-1,0,1]]
horizontal edge detection:
[[-1,-1,-1],
[0,0,0],
[1,1,1]]
we can use a 3x3x1 filter to detect edges in a 6x6x1 image

padding:
we can use padding to keep the size of the image the same after applying the filter
valid no padding
same padding to keep the size of the image the same
stide:
how many pixels we move the filter each time
3d convolution:
we can use a 3d filter to detect edges in a 3d image
the channel must match between the filter and the image

6x6x3 and 2 filters 3x3x3 (1 horizontal 1 vertical) will give us 4x4x2

maxpooling:
we can use maxpooling to reduce the size of the image
1x1 convolution:
we can use 1x1 convolution to reduce the number of channels in the image
6x6x32 and 1x1x32 will give us 6x6x32
28x28x192 and 1x1x32 will give us 28x28x32

incepion module:
we can use inception module to reduce the number of parameters in the model

sliding window:
we can use sliding window to detect objects in an image
we can use a 3x3x3 filter to detect objects in a 6x6x3 image
sliding window wokrs by moving the filter over the image and applying the filter to each part of the image
we can use a stride of 1 to move the filter 1 pixel at a time
disadvantage of sliding window:
it is slow, and computationally expensive

nonmax suppression:
we can use nonmax suppression to remove overlapping bounding boxes
we only keep the bounding box with the highest probability
with this we ensure that 1 object is detected only once

achor boxes:
we can use anchor boxes to detect objects of different sizes

siamse network:
we can use siamse network to track objects in a video

DeepSORT:
meanshift, optical flow
kalman filter, kalman tracker

ByteTrack:
BYTE. Different from previous methods which only keep the high score detection
boxes, we keep almost every detection box and separate
them into high score ones and low score ones.

https://www.youtube.com/watch?v=7sI3VHFPP0w
Object detection in depth:
https://www.youtube.com/watch?v=ArPaAX_PhIs&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=1

Object tracking in depth:
https://www.youtube.com/watch?v=9s_FpMpdYW8

Optical flow in depth:
https://www.youtube.com/watch?v=ZiYdOwOrGyc

maybe useful:
https://www.youtube.com/watch?v=_JzOFWx1vZg

yolo7+byteTrack:
https://www.youtube.com/watch?v=eBhLXouV2f0
yolo8+byteTrack:
https://www.youtube.com/watch?v=OS5qI9YBkfk
yolo5+byteTrack football players:
https://www.youtube.com/watch?v=QCG8QMhga9k&t=623s

Question for bruno:
some of the stadiums have half of the field covered by shadow and the other is sunny, how can we deal with this?
what if the player runes from the sun to the shadow will this affect the optical flow?
or in the night when the stadium is lit by lights, how can we deal with the player shadows?

dataset:
https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc/dataset/1

blog:
https://blog.roboflow.com/track-football-players/

notebook:
https://github.com/roboflow/notebooks/blob/main/notebooks/how-to-track-football-players.ipynb

presentation:
https://www.youtube.com/watch?v=_f-oX7ca3Ik
paper: https://arxiv.org/pdf/1912.05445.pdf


heigh recall and low precision:
has many false positives 

heigh precision and low recall:
miss many objects


Add env to jupyter notebook:
python -m ipykernel install --user --name=firstEnv
jupyter notebook:
start jupter notebook
better to do everything from conda prompt"# FootballInsight" 
"# FootballInsight" 
