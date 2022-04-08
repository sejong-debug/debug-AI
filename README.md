# debug-AI

# 3가지방법
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
