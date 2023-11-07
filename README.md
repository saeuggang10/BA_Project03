# BA_Project03
졸음쉼터의 이용률 현황을 파악하고 졸음쉼터의 이용률을 높이기 위한 서비스 개발

<br>

## 📌 목표

1. 데이터 분석
2. 모델링
3. 서비스 구상

<br>

## 📖 상세 내용

- 교통량 데이터와 졸음쉼터 위치 데이터를 합쳐 졸음쉼터 이용률 현황 분석
- 고속도로 노션별 졸음쉼터 분포 분석
- 졸음쉼터의 편의시설 현황 분석
- 고속도로 노선별 터널길이 상위 30개 분포와 졸음쉼터 분포 현황
- 사고다발지역과 졸음쉼터의 효용성 분석
- 졸음쉼터 설치 및 관리규정 부적합 요소 도출
- 서비스 계획
    - 졸음운전자의 상태를 알 수 있는 바이털지수 분류모델
    - 눈 깜빡임 감지 딥러닝 모델을 만들어 서비스 계획
    - 졸음이 인지되면 근처의 졸음쉼터로 안내해주는 서비스를 제작하고자 함

<br>

## 🐰 역할

- 휴게소 정보 데이터 수집
- 졸음쉼터 정보 데이터 수집
- Open API 데이터 수집
- 지도 시각화
- 지도에서 졸음쉼터 주변의 인사이트 도출
- 모델 선정 및 해석

<br>

## 🛠️ Stack
|분야|사용 기술|
|------|---|
|Data Preprocessing|<img src="https://img.shields.io/badge/numpy-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/pnadas-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/BeautifulSoup-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/herversine-색상?style=for-the-badge&logoColor=white">|
|Plot|<img src="https://img.shields.io/badge/matplotlib-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/seaborn-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/plotly-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/folium-색상?style=for-the-badge&logoColor=white">|
|Model|<img src="https://img.shields.io/badge/RandomForest-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/SGD-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/KNN-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/Extra Trees-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/Gradient Boosting-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/HistGradient Boosting-색상?style=for-the-badge&logoColor=white">|
|MS|<img src="https://img.shields.io/badge/Excel-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/PPT-색상?style=for-the-badge&logoColor=white">|
|Share|<img src="https://img.shields.io/badge/Google Drive-색상?style=for-the-badge&logoColor=white"> <img src="https://img.shields.io/badge/Notion-색상?style=for-the-badge&logoColor=white">|

<br>

## 🔥 성장경험

<br>

## ✨ 문제점 및 해결

😒 졸음쉼터 이용률 데이터는 **없음**

1. 어떤 데이터로 유추할 수 있을까❔
    
    👉 고속도로 이용량과 졸음쉼터 설문조사, 졸음쉼터 주변 교통사고량을 이용해 이용량 유추
    
<br>

😒 데이터 만으로는 연관성을 읽어내기 **어려움**

1. 위경도와 단순 수치(예, 이용률, 사고율)로만 표기
    
    👉 지도 시각화로 주변 사물과의 거리 확인 → 외부 환경 요소 확인
    
    👉 지도 시각화로 지리적 특성 확인
    
    ➖ 터널 데이터, 휴게소 데이터 추가적으로 수집
    
<br>

😒 ‘졸음’이라는 기준이 **모호**

1. 원인은❔
    
    ➖ 실험 대상자가 ‘졸음’이라고 인지해야 졸음으로 표기
    
    ➖ 기존 data의 Target변수의 범주가 {1: 정상, 2:졸음, 3:수면}
    
    👉 졸음을 제거 후 {1: 정상, 3:수면}으로 모델링을 진행하였고 정확도가 향상됨
    
<br>

## ✨ 한계점

- 전시 상황을 대비한 비상활주로 등 군 시설물이 주변에 위치하여 공개적으로 고속 국도 데이터를 제공받을 수 없음
- Open API 담당 엔지니어의 출장으로 30개의 고속도로 중 2개의 고속도로 위험 지수 데이터만 사용하여 분석