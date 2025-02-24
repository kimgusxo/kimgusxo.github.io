---
layout: post
title:  "Light Me!"
permalink: /lightme/
img: team_project/LightMe-thumbNail.png
date: 2024-09-12 00:00:00 +0900
description: (부트캠프 CX 프로젝트) K-POP 팬들을 위한 덕질 어플리케이션(프로토타입)
---

# :pushpin: Light Me!
> K-POP 팬들을 위한 덕질 어플리케이션(프로토타입)

<br>

## 1. 깃허브 링크
- [LightMe](https://github.com/kimgusxo/CX_TFIsland){: target="_blank"}

<br>

## 2. 제작 기간 & 참여 인원
- 2024년 8월 21일 ~ 2024년 9월 12일
- 팀 프로젝트
- 디자인 2명
  - 민희원(LG전자 DX School): 팀장, CX 내용 피피티 작성
  - 김주원(LG전자 DX School): 화면 디자인 및 피피티 디자인
- 기획 1명
  - 신하경(LG전자 DX School): 화면 설계서 작성 및 BX 피피티 내용 작성
- 클라이언트 1명
  - 김현태(LG전자 DX School): 클라이언트 사이드 개발, 데이터 크롤링, 데이터 분석, 데이터베이스 설계
- 서버 1명
  - 이창윤(LG전자 DX School): 서버 사이드 개발, 데이터 크롤링, 데이터 분석, 데이터베이스 설계

<br>

## 3. 기술 스택
### 3-1. Data Analyst 기술 스택
- Python
- BeautifulSoap
- Selenium
- Scipy
- Gensim

### 3-2. Client-Side 기술 스택
- Kotlin
- Retrofit
- LiveData
- Groovy

<br>

## 4. 데이터 분석
데이터 분석 과정은 1차 크롤링을 통한 팬들의 은어 탐색, 2차 크롤링을 통한 팬덤 문화 데이터 크롤링,
액터 클러스터링을 거쳐 기회영역 분석을 통해 페르소나 도출

<details>
<summary><b>데이터 분석 과정 설명 펼치기</b></summary>
<div markdown="1">

### 4-1. 1차 크롤링
<details>

<summary>
  <b>1차 크롤링 펼치기</b>

</summary>

<div markdown="1">

![FirstCrawling1](../assets/img/team_project/LightMe-Crawling1-1.png)
- 팬덤 문화는 폐쇄적이라 데이터에 팬들이 사용하는 은어가 많이 분포되어있음. 따라서 직접 원문들을 확인하여 은어를 정리하여 크롤링 진행

![FirstCrawling2](../assets/img/team_project/LightMe-Crawling1-2.png)
- 크롤링을 진행한 뒤 팬덤 문화는 크게 4가지로 구분되었고 그 중 가장 데이터의 양이 많던 굿즈 문화에 타겟팅함

</div>
</details>

### 4-2. 2차 크롤링
<details>

<summary>
  <b>2차 크롤링 펼치기</b>
</summary>

<div markdown="1">

![SecondCrawling](../assets/img/team_project/LightMe-Crawling2.png)
- 굿즈 문화를 깊이있게 이해하기 위해 굿즈 물품을 키워드로 사용하여 2차 크롤링을 진행하여 2만개의 데이터 확보

</div>
</details>

### 4-3. 1차 액션 클러스터링
<details>

<summary>
  <b>1차 액션 클러스터링 펼치기</b>
</summary>

<div markdown="1">

![FirstActionClustering](../assets/img/team_project/LightMe-ActorClustering1.png)
- 2만개의 데이터 중 광고성 글과 의미없는 글, 짧은 글 등을 필터링하여 13,000개의 데이터로 정리하였고 클러스터링을 진행

</div>

</details>

### 4-4. 1차 액션 토픽 분석
<details>

<summary>
  <b>1차 액션 토픽 분석 펼치기</b>
</summary>

<div markdown="1">

![FirstActionTopicAnalysis](../assets/img/team_project/LightMe-ActorTopic1.png)
- 클러스터링된 액터들을 LDA 토픽 분석을 통해 액션을 도출하고 기회영역분석을 진행하여 중요도/만족도 영역에 Actor0이 대부분 분포하고 있는 것을 확인

</div>
</details>

### 4-5. 2차 액션 클러스터링
<details>

<summary>
  <b>2차 액션 클러스터링 펼치기</b>
</summary>

<div markdown="1">

![SecondActionClustering](../assets/img/team_project/LightMe-ActorClustering2.png)
- Actor0의 행동을 더 깊이 이해하기 위해 2차 클러스터링을 진행

</div>
</details>

### 4-6. 2차 액션 토픽 분석
<details>

<summary>
  <b>2차 액션 토픽 분석 펼치기</b>
</summary>

<div markdown="1">

![SecondActionTopicAnalysis](../assets/img/team_project/LightMe-ActorTopic2.png)
- 각 액터별로 17개의 액션을 도출함
![SecondActionOpportunity](../assets/img/team_project/LightMe-SecondActionOpportunity.png)
- 액션 중 기회영역에 포착된 액션 3개를 타겟팅

</div>
</details>

### 4-7. 페르소나 도출
<details>

<summary>
  <b>페르소나 도출 펼치기</b>
</summary>

<div markdown="1">

![Persona](../assets/img/team_project/LightMe-Persona.png)
- 타겟 액션을 분석하여 페르소나를 도출함

</div>
</details>

</div>
</details>

<br>

## 5. ERD 다이어그램
![ERD Diagram](../assets/img/team_project/LightMe-ERDDiagram.png)

<br>

## 6. 서비스 흐름도
![ServiceFlow](../assets/img/team_project/LightMe-ServiceFlow.png)

<br>

## 7. 유스케이스 시나리오
<details>
  <summary><b>유스케이스 시나리오 펼치기</b></summary>
<div markdown="1">

### 7-1. 계정 유스케이스 시나리오
<details>
<summary>
  <b>계정 유스케이스 시나리오 보기</b>
</summary>

<div markdown="1">

![UseCase1](../assets/img/team_project/LightMe-UseCase1.png)

</div>
</details>

### 7-2. 설정 유스케이스 시나리오
<details>

<summary>
  <b>설정 유스케이스 시나리오 보기</b>
</summary>

<div markdown="1">

![UseCase2](../assets/img/team_project/LightMe-UseCase2.png)

</div>
</details>

### 7-3. 덕질 유스케이스 시나리오
<details>

<summary>
  <b>덕질 유스케이스 시나리오 보기</b>
</summary>

<div markdown="1">

![UseCase3](../assets/img/team_project/LightMe-UseCase3.png)

</div>
</details>

### 7-4. 팬덤 유스케이스 시나리오
<details>

<summary>
  <b>팬덤 유스케이스 시나리오 보기</b>
</summary>

<div markdown="1">

![UseCase4](../assets/img/team_project/LightMe-UseCase4.png)

</div>
</details>

</div>
</details>

<br>

## 8. 핵심 기능
이 서비스의 핵심 기능은 나만의 감정 일기 작성입니다.
달력에 해당 날짜의 감정을 색깔로 표현하여 보여줍니다.

<details>
<summary><b>핵심 기능 펼치기</b></summary>
<div markdown="1">

### 8-1. 메인 페이지
<details>

<summary>
  <b>메인 페이지 보기</b>
</summary>

<div markdown="1">

![Page1](../assets/img/team_project/LightMe-Page1.png)
- 본인의 정보와 최애그룹의 가장 빠른 일정을 보여준다.

</div>
</details>

### 8-2. 설정 페이지
<details>

<summary>
  <b>설정 페이지 보기</b>
</summary>

<div markdown="1">

![Page2](../assets/img/team_project/LightMe-Page2.png)
- 나의 정보를 설정하는 페이지이다.

</div>
</details>

### 8-3. 덕질 인생 페이지
<details>

<summary>
  <b>덕질 인생 페이지 보기</b>
</summary>

<div markdown="1">

![Page3](../assets/img/team_project/LightMe-Page3.png)
- 일정달력에서는 최애 그룹의 일정들을 캘린더에 표시하고 캘린더를 터치하여 상세 일정을 확인하고 감정달력에서는 녹음 버튼을 눌러 오늘의 일기를 기록하고 일기 내용을 통해 감정 구슬을 생성하여 색상 별로 캘린더에 표시한다.

</div>
</details>

### 8-4. 팬덤 놀이터 페이지
<details>

<summary>
  <b>팬덤 놀이터 페이지 보기</b>
</summary>

<div markdown="1">

![Page4](../assets/img/team_project/LightMe-Page4.png)
- 최애 그룹을 설정한 사람들의 감정 통계를 차트 형태로 보여준다.

</div>
</details>

</div>
</details>

<br>

## 9. 문제점 회고
### 1. 데이터 클러스터링 시 낮은 실루엣 지수 문제
- 원인: 팬덤 문화 데이터를 클러스터링하는 과정에서 Okt 형태소 분석과 Doc2Vec을 사용한 계층 클러스터링, K-Means, DBSCAN 등 다양한 모델을 시도했으나 낮은 실루엣 지수가 나와 문제 발생.

- 원인분석: 원인분석: 처음 시도한 Doc2Vec과 K-Means 조합에서 실루엣 지수가 0.2로 낮게 나왔고, TF-IDF와 PCA를 적용했을 때는 0.1로 더 떨어짐. 다양한 방법을 실험한 끝에 Okt + CounterVectorizer + LDA + 계층 클러스터링 조합에서 실루엣 지수가 0.5로 높아져 문제 해결의 실마리를 찾음.

- 해결방안: 최종적으로 실루엣 지수가 가장 높았던 Okt + CounterVectorizer + LDA + 계층 클러스터링 방법을 채택하여 클러스터링 안정성을 확보함.
