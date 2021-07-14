# YOLO_MASK_TEMPERATURE_DEDECTION　　　　　　　　
 
  
### 1. 개요  
 - 코로나19 팬데믹으로 집단시설, 다중이용시설 이용시, 반드시 방역관리지침을 준수해야 합니다.  
 - 이러한 방역관리리지침으로 고객분들이 시설물을 이용하실 때 불편을 야기시킵니다.
 - 또한, 시설물 운영&관리자에게는 고가의 무인 마스크, 체온 탐지기를 구매해야하는 경제적 부담이 야기됩니다.  
  
  
  
### 2. 목적
 - 이에, 부지가 넓고 관리해야할 건물의 수가 많은 중소기업의 고객과 시설물 운영&관리자의 불편을 최소화하기 위해 한 개의 기기에서  
마스크 착용여부 확인 / 체온 측정 / QR코드 인증을 일괄적으로 진행할 수 있도록 코드를 구현해보았다.  
 - 이 colalb 파일을 이용하여 고가의 장비없이 무인 체온 탐지기와 동일한 기대효과를 낼 수 있도록 구현하고자 합니다.    
  
  
### 3. 프로세스 
 - 사진촬영 -> 마스크 착용여부 확인 -> 체온 측정 -> QR코드 인식  
    
    
### 4. 결과 
 - 고가의 마스크 탐지 장비가 없이, 노트북만을 이용하여 탐스크 탐지 및 QR코드 관리 가능합니다.   
 - colab활용하였기에 부지가 넓고 관리하기 많은 중소기업에서 노트북만으로 활용할 수 있도록 구현하였습니다. 
 - 이 처럼 학습 내용을 기반으로 현실문제를 해결해보았습니다. 
 - 추후 exe파일로 변환하여 실행만 시키면 작동될 수 있도록 확장시켜갈 예정입니다.  
   
#### 4-1. 마스크 탐지  
1) YOLO 버전 : YOLO v4  
2) 사용한 툴 : google colab  
3) 결     과 : 89.04 %(accuracy)  
4) Detecting in 3 classes(mask, half mask, no mask)  
![image](https://user-images.githubusercontent.com/73736988/125576750-f9acffa8-ddc0-4e3c-9f35-9515776bbfe6.png)  


#### 4-2. QR코드 탐지   
1) 사용한 툴 : opencv2와 qyzbar 라이브러리  
2) 결     과 : 실제 네이버 QR코드를 실행시켜 인식되는 화면   
![image](https://user-images.githubusercontent.com/73736988/125577463-52cc32a0-dc8b-474e-9a3f-ebbe97696ae2.png)  
  
#### 4-3. Temperature  
1) 사용한 툴 :  homography compute알고리즘  
2) 온도의 경우, 라즈베이파이 및 열감지 카메라가 필요하기에 경제적 부담으로 실제 구현하지 못하였습니다.  
3) 대신, 온도를 측정해야하는 범위를 결정하기 위해 homography compute알고리즘을 사용하는 코드를 구현해보았습니다.  
![image](https://user-images.githubusercontent.com/73736988/125585231-2a4fe505-904b-48a0-9c29-afaaf991b2a6.png)


그 외 자세한 내용은 위 코드를 살펴보시면 확인하실 수 있으시며, 보시기 편하도록 파트별로 구분하여 코드를 첨부하였습니다.   
방문해주셔서 감사합니다.  
