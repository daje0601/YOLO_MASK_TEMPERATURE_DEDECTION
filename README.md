Face Mask Detection with YOLO 　　　　　　　　Open In Colabimage
Feature
🚀 Easily try YOLO v3 (v4 as well)

⚡ Powered by google colab

👍 High accuracy (mAP@0.50 = 94.04 %)

3️⃣ Detecting in 3 classes

📺 Video on Youtube

YOLO(You only look once) is one of the fastest object detection algorithms. Although it is no longer the most accurate object detection algorithm, it is recommended that you choose when real-time detection is needed without losing too much accuracy. In this repository, we will try YOLO v3 & v4 and detect facial mask.

Updated : Real-Time Detection on COLAB !


Now you can try real time face mask detection with this notebookfile! Added codes for realtime detection with your webcam

Dataset
The dataset for this pretrained network is provided by VictorLin000 and contains 678 images of people with and without masks. There are 3 different classes annotated:

no mask - No mask at all.
improperly - Partially covered face.
mask - Mask covers the essential parts.
You can download the dataset directly from google drive.

Model structure
Darknet-53


Darknet-53 network uses successive 3 × 3 and 1 × 1 convolutional layers but now has some shortcut connections as well and is significantly larger. It has 53 convolutional layers. YOLO v2 originally used a custom deep architecture darknet-19 which has 19 layers with 11 additional layers for object detection. YOLO v2 often suffers from small object detection. This is because the layers downsampled the input. To solve this problem, YOLO v2 used an identity mapping to link the feature maps of the previous layer to capture lower-level features (which is able to reflect small object feature). However, the architecture of YOLO v2 still lacked the most important elements required by detecting small object. YOLO v3 puts it all together. First, YOLO v3 uses a variant of Darknet with 53 layer networks trained on "Imagnet".

Why 106 layers?
image For detection tasks, 53 more layers are stacked, so YOLO v3 has a 106 layer fully convolution. That's why YOLO v3 is slower than YOLO v2. You can see this architecture of YOLO v3 in colab. ( If you want more information about YOLO v3 & image detection, check powerpoint file in this repo)

!./darknet detector map /content/Face_Mask_Detection_YOLO/MASK/object.data\
                        /content/Face_Mask_Detection_YOLO/MASK/detect_mask.cfg\
                        /content/darknet/backup
Demo








Evaluation
Average Precision
class_id	name	TP	FP	ap
0	mask	333	34	96.96%
1	improperly	12	6	92.80%
2	no mask	62	13	92.37%
F1-score & Average IoU
conf_thresh	precision	recall	F1-score	TP	FP	FN	average IoU
0.25	0.88	0.95	0.92	407	53	21	69.55 %
Mean Average Precision
mean average precision (mAP@0.50) = 94.04 % 

Usage
Load weight
!wget https://pjreddie.com/media/files/darknet53.conv.74
or you can get pretrained weights for this data

Train
!./darknet detector train /content/Face_Mask_Detection_YOLO/Mask/object.data\
                          /content/Face_Mask_Detection_YOLO/Mask/detect_mask.cfg\
                          darknet53.conv.74\
                          -dont_show -map 
Detect
!./darknet detector test /content/Face_Mask_Detection_YOLO/Mask/object.data\
                         /content/Face_Mask_Detection_YOLO/Mask/detect_mask.cfg\
                         /content/backup/detect_mask_last.weights\
                         /content/Face_Mask_Detection_YOLO/demo/man_0_1.png
Addition (YOLOv4)
I've tried YOLOv4 on this dataset. It takes longer than Darknet-53 but there is a chance to improve the performance. You can load this weight with 2000 iteration from google drive.. This pre-trained network distinguishes 0 and 1, but 2 does not seem to distinguish well. (I also tried YOLOv4-tiny, but It doesn't work well. Got only 65.1% mAP)

image

detections_count = 1221, unique_truth_count = 428  
class_id = 0, name = mask, ap = 97.68%   	 (TP = 328, FP = 24) 
class_id = 1, name = improperly, ap = 91.54%   	 (TP = 12, FP = 6) 
class_id = 2, name = no mask, ap = 86.57%   	 (TP = 62, FP = 15) 

for conf_thresh = 0.25, precision = 0.90, recall = 0.94, F1-score = 0.92 
for conf_thresh = 0.25, TP = 402, FP = 45, FN = 26, average IoU = 71.84 % 

IoU threshold = 50 %, used Area-Under-Curve for each unique Recall 
mean average precision (mAP@0.50) = 0.919299, or 91.93 % 
Reference
https://arxiv.org/abs/1804.02767
https://arxiv.org/abs/1506.02640
https://towardsdatascience.com/yolo-v3-object-detection-53fb7d3bfe6b
https://github.com/AlexeyAB/darknet
https://github.com/VictorLin000/YOLOv3_mask_detect
https://pjreddie.com/darknet/yolo/
https://colab.research.google.com/drive/1_GdoqCJWXsChrOiY8sZMr_zbr_fH-0Fg
https://medium.com/@artinte7
https://machinelearningmastery.com/how-to-perform-object-detection-with-yolov3-in-keras/
https://blog.paperspace.com/how-to-implement-a-yolo-object-detector-in-pytorch/
Source from
https://pixabay.com/
https://www.miricanvas.com/
https://www.videvo.net/
