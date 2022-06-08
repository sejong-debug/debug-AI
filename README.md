# debug-AI

# 해결 방법
  * Object Detection
  * Classification
  * Multilabel-Classification ✔️
    
# 데이터 셋 및 성능
최초 제공받은 작물3종(팥, 참깨, 콩), 질병 8종(팥_흰가루병, 팥_세균잎마름병, 팥_Rhizopus, 참깨_세균성점무늬병, 참깨_흰가루병, 콩_노균병, 콩_들불병, 콩_불마름병, 콩_병징), 정상 1종(콩)에 데이터를 추가하여 작물 종류와 질병 종류를 증가시켰습니다. <br> 

AI HUB : 추가 작물 19종, 질병 42종 데이터 <br> 
시설 작물 질병 진단 이미지 소개 (https://aihub.or.kr/aidata/30729) <br> 
노지 작물 질병 진단 이미지 소개 (https://aihub.or.kr/aidata/30731)  <br> 
과수화상병 촬영 이미지 소개 (https://aihub.or.kr/aidata/30732) <br> 

참깨 정상 데이터는 다음 데이터셋을 <br>
https://www.kaggle.com/datasets/ravirajsinh45/crop-and-weed-detection-data-with-bounding-boxes

팥 정상 데이터는 다음 논문 저자에게 Red Bean Leaf 데이터를 요청하여 제공받았습니다. <br>
[Leaf image-based classification of some common bean cultivars using discriminative convolutional neural networks](https://www.sciencedirect.com/science/article/abs/pii/S0168169920331409)


![image](https://user-images.githubusercontent.com/80030558/172639211-7434d424-d56e-479a-8ae8-5ed24b5b4ee3.png)
![image](https://user-images.githubusercontent.com/80030558/172638713-642edffd-e5a5-4d17-8a80-8a9b14a70ace.png)

# Citation
  * Survey
  <span><br>&nbsp;&nbsp;&nbsp;&nbsp; </span>
  [Deep learning models for plant disease detection and diagnosis](https://www.sciencedirect.com/science/article/abs/pii/S0168169917311742)
  
  * GAN
  <span><br>&nbsp;&nbsp;&nbsp;&nbsp; </span>
  [LeafGAN: An Effective Data Augmentation Method for Practical Plant Disease Diagnosis](https://arxiv.org/pdf/2002.10100.pdf)
  
  * Class Imbalance 
  <span><br>&nbsp;&nbsp;&nbsp;&nbsp; </span>
  [Emotion Classification with Data Augmentation Using Generative Adversarial Networks](https://arxiv.org/pdf/1711.00648.pdf)
