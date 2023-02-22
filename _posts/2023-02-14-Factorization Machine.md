---
layout: single
title: "[논문리뷰] Factorization Machine "
categories: recommender system
--- 


```python
import os
from IPython.display import Image 
```

## Factorization Machine

Factorization Machine(FM)을 검색해보면 다 아래 논문에서 발췌해온 이미지를 첨부해둔다. 다른 추천 모델에서는 행이 User 열이 Item을 갖는 행렬모형을 만든다. Factorization Machien 은 User-Item 을 하나의 행으로 이어서 하나의 벡터 정보로 구성한다. 공통점은 형태만 달리했을 뿐 categorical feature 가 많고, 습득되지 않은 정보에 의해 sparse 한 데이터가 구성된다.

* FM 장점
    - 매우 큰 데이터에 대해서도 학습이 가능(복잡도 단계: 선형복잡도)
    - 다양한 예측 문제에 적용 가능
        * Regression, Binary Classification, Ranking
    


```python
Image("plots/23-02-14_01.png")
```




    
![png](output_4_0.png)
    



### Linear Model   
일반적인 Linear Regression 형태라면 아래와 같이 정의한다. Linear Model은  데이터가 가진 특성을 표현하기에 부족하며, 변수와 변수 간의 interaction 정보가 무시된다. 


$$\hat{y} =  w_0+\sum_{i=1}^{n}{w_ix_i}$$

---
### Polynomial Model   
LR의 단점을 보완하기 위해 PM 을 쓰면 LM 의 단점을 보완할 수 있으나 FM에서 구성하는 $x$(feature)가 많아질수록 계산 복잡도가 비선형으로 늘어나게 된다.

$$\hat{y} =  w_0+\sum_{i=1}^{n}{w_ix_i}+\sum_{i=1}^{n}\sum_{j=i+1}^{n}{w_{ij}x_{i}x_{j}}$$

---
### Factorization Machine    
Factorization Machine은 feature interaction vector 를 저차원으로 factorization 함으로써 계산복잡도 문제를 해결한다. Sparse 한 환경에서 feature 들은 독립성이 강해 interaction 을 추정하기 어려운 단점을 이론적으로 커버한다.  또한, 변수 간 내적으로 분해함으로써 연산 복잡도는 선형(linear)으로 유지한다.

$$\hat{y} =  w_0+\sum_{i=1}^{n}{w_ix_i}+\sum_{i=1}^{n}\sum_{j=i+1}^{n}{(\vec{v_i}\cdot \vec{v_j})x_{i}x_{j}}$$

---
### Reference

original paper : https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf
