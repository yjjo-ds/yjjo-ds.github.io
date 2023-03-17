## Cold Start

이번 포스팅은 추천시스템을  구성할 때 빠지지 않는 문제인 Cold Start 에 대해 얘기해보려합니다. cold start 의 종류들을 찾아보다가 Wikipedia 문서에 잘 정리되어 있어 해당 내용을 정리해보았습니다. 

## cold start 문제란?

추천시스템은 고객이 흥미를 갖는 상품(정보)를 추천해주는 기술로 아이템 특성이나 사용자 흥미, 평점, 북마크, 구입, 선호, 페이지 방문등과 같은 정보를 기반으로 한다. 


콜드 스타트 문제는 세가지 케이스로 나눌 수 있다. 

1. New community : 새로운 서비스가 운영되어 서비스의 어떠한 로그가 없는 환경
2. New item : 새로운 상품이 시스템에 추가된 경우
3. New User : 새로운 고객이 등록하거나 등록 후 어떠한 행동(활동)을 하지 않은 경우


## 신규 고객에 대한 각 모델 한계



- item_based recommendation
    - 유저의 상품에 대한 평가를 기반으로 하기 때문에 추천정보를 얻을 수 없다.
- user-based recommendation
    - 유저의 초기 프로필이 모델이 유사 고객을 추론할 수 있는 정도로 충족하면 사용가능
    



## Cold Start 해결하는 방법



다양한 추천 알고리즘이 있기 때문에 콜드 스타트 문제를 완화(mitigate) 하기 위한 다양한 전략이 개발되었습니다. 주요 접근은 각 한계를 완화하기 하이브리드 추천에 의존하는 것 

- Profile completion
    - 프로파일을 채우는 방법으로 어떤 상품을 클릭하지 않아도 기본적인 고객의 특성, 유사한 고객을 찾을 정도(임계치)를 넘는 고객데이터를 수집하는 방법을 말합니다.
    
- Feature mapping
    - 구축된 latent factors(user-item matrix) 를 이용하여 interaction 이 없는 item feature 에 대해 추정하는 방법이다. 또는 group-specific 방법을 활용하여 item(또는 user)이 속하는 그룹의 latent factor 로 근사화
- Hybrid feature weigting
    - featurne mapping 과 유사하게 hybrid content-based filtering recommender 를 구축하는 것으로 상품 또는 유저의 중요도 인식에 따라 가중치가 부여되는 방식입니다. (고객이 중요하다고 인식하는 것에 weighting을 주는 방법)
- Differentiating regularization weights
    - **더 많은 정보를 드러내는 항목 또는 사용자(즉, 인기 있는 항목 및 활성 사용자)와 관련된 잠재 요인에 더 낮은 제약 조건을 할당하고 다른 항목(즉, 덜 인기 있는 항목)에 더 높은 제약 조건을 설정하여 콜드 스타트 문제를 완화합니다. 및 비활성 사용자)**
    - 과도하게 복잡한 모델을 학습하여 overfitting 되는 것을 방지하기 위함
    - l2-norm 과 같은 regularization


```python

```


```python

```


```python

```


```python

```
