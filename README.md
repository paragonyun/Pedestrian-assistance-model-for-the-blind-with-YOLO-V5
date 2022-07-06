# 시각장애인의 안전한 보행을 위한 보행 보조 모델(Pedestrian Assistance Model for THE BLIND with YOLO V5)  
## 주요 파라미터 (Main Parameters)  
* Epoch : 10 Epoch   
학습 시간이 오래 걸리고 어려운 데이터가 아니라서 10Epoch 정도면 충분했습니다. (It takes long time to train and also it was not hard to train! So I think 10Epoch is enough)  
* Batch Size : 64  
* Image Size : 640 YoloV5s에 권장되는 Image Size (The Image Size Recommended for YoloV5s)
  
## 사용한 모델 (Model)
* Pretrained Model : YOLO V5  
  
## 학습 환경 (Training Envionment)
* Colab Pro

## 데이터셋 (Dataset)
* 셀렉트 스타 - 교차로 및 화폐 정보 데이터셋  
* https://open.selectstar.ai/data-set/wesee  
  
## 학습 결과 (Result of Train)
#### Wandb로 시각화한 결과입니다. (I Visualize the Result with Wandb)
![result1](https://user-images.githubusercontent.com/83996346/177499202-9e23e52e-54c0-4733-99df-3e418a50100a.png)
![result2](https://user-images.githubusercontent.com/83996346/177499204-97537eb5-65cb-41d0-859b-6a099a0e75a5.png)
![result3](https://user-images.githubusercontent.com/83996346/177499207-cc801f94-42a2-4d67-8470-23d0410c858e.png)
![result4](https://user-images.githubusercontent.com/83996346/177499209-85f0c1ec-9904-4996-aef9-b891b70f356e.png)
![result5](https://user-images.githubusercontent.com/83996346/177499189-386ad9f8-b90c-413e-9f66-581ea26f97ed.png)
![result6](https://user-images.githubusercontent.com/83996346/177499199-df4257be-861e-4900-8db6-e6dac7a820ac.png)
  
#### Metrics
![Metrics](https://user-images.githubusercontent.com/83996346/177499371-c88f43bb-1e78-4cac-926f-d6341dc91a64.png)
  
#### Train and Valid Batch
![Train Batch](https://user-images.githubusercontent.com/83996346/177499462-b3117339-d636-4b5e-bdd6-88ec7fb94267.jpg)
![valid_batch](https://user-images.githubusercontent.com/83996346/177499520-8ca0738a-1b18-4771-9e50-4fe5cf45a0a5.jpg)
  
#### Train Development
![train_epoch1](https://user-images.githubusercontent.com/83996346/177499478-30a93903-b625-4ad3-8328-3a58158f94b7.png)  
Train Epoch 1  
  
![train_epoch7](https://user-images.githubusercontent.com/83996346/177499885-182a3f2a-420d-4d43-8905-86a2da848c98.png)  
Train Epoch 7  

#### Inference Result
![1](https://user-images.githubusercontent.com/83996346/177501350-17fc12fd-faa3-4bdb-97e6-78b53cbb628e.png)
![2](https://user-images.githubusercontent.com/83996346/177501338-5dd314cc-b783-4f4d-9e0d-3ac7cb267f7e.png)
![error](https://user-images.githubusercontent.com/83996346/177501352-bb268247-2135-402b-ba7d-f58caafcd928.png) 
전반적으로 학습이 잘 진행된 모습이지만 줄무늬 옷을 횡단보도로 인식하는 등, 아직 개선사항이 있어 보였습니다.  
It performed pretty well... but Sometimes it inferernce stripe T-shirt as a Zebra-Cross..! It seems to need more train 

# 개선 사항 (Improvement Elements)
1. 보행에 장애가 될만한 더 많은 Class를 학습시킬 예정입니다.
2. 좀 더 빠른 학습을 할 수 있도록 대책을 강구할 예정입니다. 
3. 버스 시각 정보와 연계하여, 탐지한 대상이 버스인 경우 OCR을 이용하여 번호를 알려주는 서비스로 확대할 예정입니다.
  
1. I'm planning to teach more classes that can interfere with walking.
2. I will take measures to learn faster.
3. I will expand the service to provide the number if the target is a Bus using OCR
