#YOLO_MASK_TEMPERATURE_DEDECTION　　　　　　　　
Open In Colabimage  
  
1. 개요  
-. 코로나19 팬데믹으로 집단시설, 다중이용시설 이용시, 반드시 방역관리지침을 거쳐야 한다.  
-. 이러한 방역관리리지침으로 고객분들이 시설물을 이용하실 때 불편을 야기한다.  
-. 또한, 시설물 운영&관리자에게는 고가의 무인 마스크, 체온 탐지기를 구매해야하는 경제적 부담이 야기된다.  

2. 해당 프로젝트의 목적
1) 해당 프로젝트는 고객과 시설물 운영&관리자의 불편을 최소화하기 위해 한 개의 기기에서  
마스크 착용여부 확인 / 체온 측정 / QR코드 인증을 일괄적으로 진행할 수 있도록 코드를 구현해보았다.  
  
2) 이를 exe프로그램으로 구현하여 고가의 장비없이 무인 체온 탐지기와 동일한 기대효과를 낼 수 있도록 구현하고자 한다.  


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


