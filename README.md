# 제3회 통계최강자전

# 1. Introduction

## 소개 & 성적

### Score  
![1th](https://img.shields.io/badge/1th-red?style=plastic)


### Members

임승섭|이정우|신은빈
:-:|:-:|:-:
|[seopp](https://github.com/seopp)||[eunbinni](https://github.com/eunbinni)|
|y7511204@naver.com|gksekdrn@naver.com|dnflrhra@naver.com|

---
# 2. Project Outline


## 대회 개요
 
[All Premier League Matches 2010 ~ 2021] <br>
[Learning from Imbalanced Insurance Dataset] <br>
[Top Hits Spotify from 2000 ~ 2019] <br>
[Personality Classification Data : 16 Personalities]98746daeabc44b61b665ab0b757ee36a) <br>
[Higher Education Students Performance Evaluation] <br>
위 5개의 데이터셋 중 하나를 택해 자유롭게 분석을 진행


## 대회 기간 
> **2022.09.04 ~ 2022.10.16**

## 평가 방법 
  - 1차 심사 - 제출한 결과물을 바탕으로 교수님들이 평가를 진행
  - 2차 심사 - 1차 심사 합격팀에 한해 응용통계인의 밤 행사에서 발표를 진행, 최종 심사 결과 발표 후 시상


# PPT 목차

### 1. introduction

- 선정 배경
    - 기업이 마케팅 활동을 전개하는 데 있어 고객들의 상품 선택 행동에 대한 이해와 예측은 매우 필수적인 요소이다.
    - 어떠한 특성을 가진 고객이 어떤 상품을 선택할 것인지를 이해하고 사전에 예측하는 능력은 고객별로 맞춤형 마케팅 프로그램을 제공하는 타깃 마케팅을 전개하는 데 있어 반드시 가져야 할 핵심적인 역량이기 때문이다.
    - 오늘날의 기업들은 이른바 빅데이터 시대라고 불리는 경영 환경을 마주하고 있는데, 특히 마케팅 분야는 이러한 방대한 데이터들이 생성되고 활용되는 최전선에 있다고 해도 과언이 아닐 정도로 다양한 고객 관련 데이터들이 생성되고 있다.
    - 이러한 흐름에 따라 우리는 보험사의 고객 데이터를 활용한 데이터 분석을 통해 고객 맞춤형 마케팅을 제안하고자 한다.
- 분석 목표
    - 기존 건강보험 가입자들 중 자동차 보험에 대해 긍정적으로 응답한 고객들에 대하여 가장 잘 예측할 수 있는 최적 모델 찾기
    - 최적 모델에서 자동차 보험에 긍정적일 것으로 예측된 회원들의 특성에 가장 중요하게 영향을 미치는 변수를 찾아, 자동차 보험 판매 프로모션 방향성의 인사이트 찾기
    - 군집분석을 통하여 군집별 특성을 확인한 후 비교함으로써 프로모션 방향성의 인사이트 찾기
    - 모델링과 군집분석을 통한 자동차 보험 프로모션 방향성 제시

### 2. Data Exploration

- 데이터 소개
    - 불필요한 변수(id)삭제
- 시각화
    - target값 불균형 분포
    - 수치형 변수들과 target값의 분포
    - 범주형 변수들과 target값의 분포
    - 상관관계 → 다중공선성 의심
- 전처리
    - 결측치 처리
        - 결측치 존재 x
    - 파생변수 생성
    - 인코딩
        - label 인코딩
    - 이상치처리
        - boxplot 시각화
        - ‘Annual_Premium’ 칼럼 이상치 확인 후 이상치 대체
    - 스케일링
        - log 변환

### 3. Modeling

- 통계적 모델
    - 로지스틱회귀 가설검정
        - logistic regression을 선택한 이유
        - 로지스틱 회귀 모델에 대한 가설 검정
        - 개별 회귀 계수에 대한 가설 검정
        - 변수선택법(단계선택법) step
        
        → anova에서도 vintage, 변수선택법(단계선택법)에서도 vintage이므로 vintage를 제거하는 것으로 결정
        
- 머신러닝 모델
    - RandomForest, XGBoost, CatBoost 비교 → Catboost 선정
    - CatBoost 모델의 다중공선성 처리 전후 비교
    - CatBoost 모델의 불균형 처리 전후 비교 (class_weight 파라미터)
    - Parameter Tuning -  (Bayesian Optimization)
    - threshold 변경 → 변경에 대한 이유
    - SHAP value를 통한 유의미한 변수 고찰

### 4. Clustering

- 군집화를 위한 추가 전처리
    - 변수 선택
    - one-hot 인코딩
    - log 변환
    - 시각화를 위한 PCA
- K-means
- 해석

### 5. Conclusion

- 결론
    - 모델링
        - → Previously_Insured, Vehicle_Damage, Age 가 중요한 변수로 판단
    - 군집화
        - → 0번 군집 : 20대가 90%이상 차지. 이 군집의 97%는 신청을 하지 않음.
        - → 2,3번 군집 : 중장년층 위주로 분포. 기존의 Response 비율(16%)와 비교 했을 때 신청 비율이 2배 이상
    
      1.  차 보험에 대해 영향을 미치는 중요한 변수는 **‘연령/차 사고 경험/이전 보험 가입 여부’이며** 
    
     **특히 경제활동인구가 많은 27~54세 사이의 연령이 차 보험에 가장 긍정적일 확률이 높은 것으로 보아 이 연령층에 마케팅을 집중.**
        
    1. 20대가 차 보험에 부정적인 이유는 아직 필요성을 못느꼈기 때문이라고 판단. 따라서 차 보험의 필요성을 알리는 마케팅 진행
    2. 또한 **판매채널의 경우 채널별로 편차가 큰 것으로 보임. 26, 124, 163번 채널의 ‘핵심 연령층’에 마케팅을 집중. 상대적으로 낮은 반응을 보이는 판매채널에는 마케팅을 아주 적게 하거나 진행하지 않는 방법을 통해 비용을 줄임**

- 한계점
    - 위 데이터에서는 판매채널에 대한 정보 및 판매정책들이 상세하게 나와있지 않기 때문에 좀 더 심층적인 마케팅 인사이트는 뽑을 수 없었습니다만, 실제 현업에서는 판매채널별/지역별 상세 정보 등을 추가로 분석해 더 뾰족한 마케팅 인사이트를 얻을 수 있을 것으로 판단
    - 데이터의 한계로 인해 다양한 전처리 방법과 세밀한 군집화를 해보지 못함. 더욱 다양한 정보를 가진 데이터가 있었다면 더 정밀하고 효과적인 인사이트 도출이 가능했을거라 생각
