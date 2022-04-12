# debug-AI

# 3가지 접근방법
## 1.Object Detection
<kbd><img src = https://user-images.githubusercontent.com/80030558/162415573-240617e7-5bef-4a9c-aa70-721309a5c2a6.png></kbd>

  **장점 :**
    <p> &nbsp; &nbsp; &nbsp; &nbsp; 질병의 위치정보를 제공할 수 있다. </p>
  **단점 :** 
    <p> &nbsp; &nbsp; &nbsp; &nbsp; 질병 데이터셋의 경우 ground truth에서 bounding box를 정교하게 표시하는 것이 까다롭다. </p>
    <p> &nbsp; &nbsp; &nbsp; &nbsp; 가장 학습이 오래걸린다. </p>
    
    
## 2.Classification
<kbd><img src = https://user-images.githubusercontent.com/80030558/162415544-f5078a6e-6562-48c8-8fce-842c42000e9e.png></kbd>

  **장점 :** 
    <p> &nbsp; &nbsp; &nbsp; &nbsp; 가장 구현이 간단하다. </p> 
  **단점 :** 
    <p> &nbsp; &nbsp; &nbsp; &nbsp; 한가지 출력만을 기대하기에 이미지에 여러 종류의 (질병, 해충)이 존재할 경우 TOP3 방법 등을 사용해야한다. </p> 
    <p> &nbsp; &nbsp; &nbsp; &nbsp; classification에서는 softmax를 사용하므로 이미지에 여러 종류의 (질병, 해충)이 존재할 경우 확률이 낮아지게 된다. </p> 
    
## 3.Multi-label classification
<kbd><img src = https://user-images.githubusercontent.com/80030558/162416194-05dd66cf-dbb0-4a3a-9a63-6a70c166bd97.png></kbd>

  **장점 :** 
    <p> &nbsp; &nbsp; &nbsp; &nbsp; 여러 종류의 (질병, 해충)의 출력을 커버할 수 있다. </p> 



# 농작물 질병 데이터셋의 특수성
<strong><p>1. 질병 데이터셋은 정교한 bounding box labeling이 어려울 수 있다 </strong></p>
<strong><p>2. 질병 검출 task에서 위치 정보는 다른 Object Detection task(Pedestrian Detection)에 비해 중요도가 높지 않을 수 있다</strong></p>
<strong><p>3. 질병 검출 task에서는 한 이미지에서 같은 종류의 질병을 추가 식별하는 것(이미 한 이미지에서 A질병을 식별했다면 다른 위치에서도 A질병을 식별하는 것)의 중요도가 높지 않을 수 있다</strong></p>


# Multi-label Classification으로 진행하게 될 경우
### 평가 metric은?
### f1-score vs roc_auc_score
### data가 imbalance하다면 항상 f1-score를 사용해야한다.

### MCC Metrics?
### [The advantages of the Matthews correlation coefficient (MCC) over F1 score and accuracy in binary classification evaluation](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-019-6413-7)
