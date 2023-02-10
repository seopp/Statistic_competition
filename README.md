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

# All Premier League Matches 2010 ~ 2021

[Learning from Imbalanced Insurance Dataset](https://www.notion.so/Learning-from-Imbalanced-Insurance-Dataset-b662a7b419024054858c0302d281d218)

[Top Hits Spotify from 2000 ~ 2019](https://www.notion.so/Top-Hits-Spotify-from-2000-2019-cbf5fbfcc8bd45428adf87a730179f50)

[Personality Classification Data : 16 Personalities](https://www.notion.so/Personality-Classification-Data-16-Personalities-98746daeabc44b61b665ab0b757ee36a)

[Higher Education Students Performance Evaluation](https://www.notion.so/Higher-Education-Students-Performance-Evaluation-b378067256144dda9dc18c5d272c1b53)


> 앱 사용성 데이터를 통한 대출신청 예측분석

- 가명화된 데이터를 기반으로 고객의 대출상품 신청여부 예측
- (2022년 3~5월 데이터제공 / 2022년 6월 예측)
- 예측모델을 활용하여 탐색적 데이터 분석 수행
- 대출신청, 미신청 고객을 분류하여 고객의 특성 분석결과 도출


## 대회 기간 
> **2022.09.04 ~ 2022.10.16**

## 평가 방법 
  - 1차 심사 - 고객 당 대출 신청 여부 예측, 데이터 수집, 전처리 과정, 예측 모델 해석(필수)
  - 2차 심사 - 제출한 예측모델 및 분석방법에 대한 발표

## 대회 데이터셋

> train.csv  
- id : 샘플 아이디
- Age : 나이
- TypeofContact : 고객의 제품 인지 방법 (회사의 홍보 or 스스로 검색)
- CityTier : 주거 중인 도시의 등급. (인구, 시설, 생활 수준 기준) (1등급 > 2등급 > 3등급)
- DurationOfPitch : 영업 사원이 고객에게 제공하는 프레젠테이션 기간
- Occupation : 직업
- Gender : 성별
- NumberOfPersonVisiting : 고객과 함께 여행을 계획 중인 총 인원
- NumberOfFollowups : 영업 사원의 프레젠테이션 후 이루어진 후속 조치 수
- ProductPitched : 영업 사원이 제시한 상품
- PreferredPropertyStar : 선호 호텔 숙박업소 등급
- MaritalStatus : 결혼여부
- NumberOfTrips : 평균 연간 여행 횟수
- Passport : 여권 보유 여부 (0: 없음, 1: 있음)
- PitchSatisfactionScore : 영업 사원의 프레젠테이션 만족도
- OwnCar : 자동차 보유 여부 (0: 없음, 1: 있음)
- NumberOfChildrenVisiting : 함께 여행을 계획 중인 5세 미만의 어린이 수
- Designation : (직업의) 직급
- MonthlyIncome : 월 급여
- ProdTaken : 여행 패키지 신청 여부 (0: 신청 안 함, 1: 신청함)



> test.csv
- id : 샘플 아이디
- Age : 나이
- TypeofContact : 고객의 제품 인지 방법 (회사의 홍보 or 스스로 검색)
- CityTier : 주거 중인 도시의 등급. (인구, 시설, 생활 수준 기준) (1등급 > 2등급 > 3등급)
- DurationOfPitch : 영업 사원이 고객에게 제공하는 프레젠테이션 기간
- Occupation : 직업
- Gender : 성별
- NumberOfPersonVisiting : 고객과 함께 여행을 계획 중인 총 인원
- NumberOfFollowups : 영업 사원의 프레젠테이션 후 이루어진 후속 조치 수
- ProductPitched : 영업 사원이 제시한 상품
- PreferredPropertyStar : 선호 호텔 숙박업소 등급
- MaritalStatus : 결혼여부
- NumberOfTrips : 평균 연간 여행 횟수
- Passport : 여권 보유 여부 (0: 없음, 1: 있음)
- PitchSatisfactionScore : 영업 사원의 프레젠테이션 만족도
- OwnCar : 자동차 보유 여부 (0: 없음, 1: 있음)
- NumberOfChildrenVisiting : 함께 여행을 계획 중인 5세 미만의 어린이 수
- Designation : (직업의) 직급
- MonthlyIncome : 월 급여

> sample_submission.csv
- id : 샘플 아이디
- ProdTaken : 여행 패키지 신청 여부 (0: 신청 안 함, 1: 신청함)


# 3. Retrospect


## 회고
우선 머신러닝을 공부한지 얼마 안되어서 처음으로 진행중인 대회에 참가한 것이었기에 미숙한점이 매우 많다.  
데이콘에서 진행하는 지난대회에 이어 다시 한 번 참가했다. 
물론 머신러닝 초심자를 위한 Dacon Basic 대회이기에 상금도 없고 연습용 대회 느낌이었지만 머신러닝에 대해 아무것도 모르는 초보자의 입장에서는 참가하면서 배울게 많은 대회였던 것 같다.


- 마주쳤던 문제들
    - 전처리 순서
        - 결측치 살려서 인코딩 -> 로그변환 -> 이상치 처리 -> knn으로 결측치 처리 -> Age 범주 변환 -> Age_level 인코딩 순서로 전처리를 진행했다.
        - 처음에는 전처리 순서에 크게 신경쓰지 않고 진행하다가 중간중간 이상한 점들을 발견해서 전처리 순서를 변경해주었다.
        - 결정적으로 전처리 순서에 영향을 끼친 이유는 결측치 처리때문이었다.
        - 본 대회는 제공되는 Test Data에도 결측치가 존재했기 때문에 결측치를 삭제하는 방법은 사용할 수 없었다.
        - 따라서 결측치를 대체하는 방법을 사용했기에 결측치를 유지하면서 처리하는 과정이 중요했던 것 같다. (사실 이 부분은 경험부족으로 인해 애를 먹었던 것 같다. 돌이켜 생각해보면 당연하면서도 기본적인 내용..)


    - OverSampling
      - 클래스 불균형 문제를 해결하기 위해 여러가지 방법을 시도해보았다.
      - 그 중 Oversampling 기법을 사용했었는데 성능 향상을 기록하지 못했다. 
      - 처음에는 막연히 불균형 데이터이기 때문에 오버샘플링을 하면 성능이 향상될 것이라는 기대를 했다.
      - 하지만 실제 해본 결과는 그렇지 않았다. 데이터의 분포에 따라 좋은 성능을 낼 수도, 성능이 떨어질 수도 있다는 점을 항상 인지해야겠다.

    - KNNImputer 
        - 이번 대회에서 결측치를 처리하면서 KNNImputer라는 것을 처음 알게 되었고, 사용해보았다.
        - KNNImputer는 sklearn의 패키지 중 하나로, 결측치를 채우는 방법으로 실무에서도 많이 쓰인다는 방법이다.
        - df.fillna(), df.interpolate 또는 SimpleImputer와 다르게 마땅히 결측치를 채울 방법이 떠오르지 않을 때 사용한다.
        - KNN을 이용해 결측치들을 채우는 방식이 가장 성능이 좋았기에 채택했지만 약간의 찝찝한 부분이 남았다.
        - KNN알고리즘의 전개 과정은 알지만 정확히 어떤 방식으로 결측치를 채우는 지에 대해서는 제대로 알 지 못했기 때문이다.
        - 특정 결측치를 채울 때 모든 칼럼의 정보를 반영하는 것인지, 아니면 관련있는 몇 개의 칼럼들로만 반영되는 것인지 등에 대한 궁금점들이 남았다. 
