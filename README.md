# debug-AI

# 해결 방법
  * Object Detection
  * Classification
  * Multilabel-Classification ✔️
    
# 데이터 셋 및 최종 성능
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

# [기법 1] PlantGAN
<pre>
식물 질병 검출문제에서 한가지 어려운 점은, 정상 식물 이미지와, 질병 식물 이미지의 획득 난이도가 다르다는 것입니다.
질병 식물 이미지는 바이러스 주입을 통해 독립된 공간에서 전문가의 관리를 통해 길러져야 하기에 질병 식물 이미지는 획득 비용이 비쌉니다.

CycleGAN을 이용하면 획득 비용이 싼 정상 식물 이미지로 질병 식물 이미지를 만들어 낼 수 있습니다.

LeafGAN논문을 참고한 PlantGAN은 LeafGAN과 동일하게 CycleGAN의 변종입니다.
LeafGAN에서 Leaf Segmentation을 Grad-CAM을 사용한다면
PlantGAN은 Leaf Segmentation을 U^2 Net을 이용합니다.

Leaf Segmentation을 통해 Leaf에 Attention을 주어 CycleGAN이 배경을 만들지 않고, 오롯이 Leaf만 변경할 수 있습니다.
</pre>

# [기법 2] Crop-aware
<pre>
식물 질병 검출문제에서 한가지 특별한 점은, 작물의 종류를 알아내는 것은 아주 쉽다는 것입니다.
Crop-aware는 학습시, 추론시 이미지와 작물 종류를 함께 제공하는 방법입니다.

학습시에 다른 작물 종류의 backpropagation을 0으로 만들어 학습하지 않습니다.
추론시에 다른 작물 종류의 confidence를 0으로 만들어 고려하지 않습니다.
</pre>

# [기법 3] Augmentation
![image](https://user-images.githubusercontent.com/80030558/172644234-f3677835-2e70-4e09-8eb3-88e0ed69ced1.png)

# Ablation Study

![image](https://user-images.githubusercontent.com/80030558/172643212-0fad9854-b2ef-4a3b-9a95-b49902acce0d.png) |![image](https://user-images.githubusercontent.com/80030558/172643419-f96f3f75-ea4a-45af-ae0a-959b980d0ebd.png)
--- | --- | 

![image](https://user-images.githubusercontent.com/80030558/172643944-a4bd80e6-ed84-451c-804c-41111a0cc775.png)

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
