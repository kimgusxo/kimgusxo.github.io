---
layout: post
title:  "Light Me!"
permalink: /lightme/
img: LightMe-thumbNail.png
date: 2024-09-12 00:00:00 +0900
description: (부트캠프 CX 프로젝트) K-POP 팬들을 위한 덕질 어플리케이션
---

# :pushpin: Light Me!
> K-POP 팬들을 위한 덕질 어플리케이션(프로토타입)

<br>

## 1. 깃허브 링크
- [LightMe](https://github.com/kimgusxo/CX_TFIsland){: target="_blank"}

<br>

## 2. 제작 기간 & 참여 인원
- 2024년 7월 16일 ~ 2024년 9월 12일
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

## 4-1. 1차 크롤링
<details>
<summary>
<b>1차 크롤링 펼치기</b>
</summary>
<div markdown="1">
![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)
</div>
</details>

## 4-2. 2차 크롤링
<details>
<summary>
<b>2차 크롤링 펼치기</b>
</summary>
<div markdown="1">
![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)
</div>
</details>

## 4-3. 1차 액션 클러스터링
<details>
<summary>
<b>1차 액션 클러스터링 펼치기</b>
</summary>
<div markdown="1">
![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)
</div>
</details>

## 4-4. 1차 액션 토픽 분석
<details>
<summary>
<b>1차 액션 토픽 분석 펼치기</b>
</summary>
<div markdown="1">
![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)
</div>
</details>

## 4-5. 2차 액션 클러스터링
<details>
<summary>
<b>2차 액션 클러스터링 펼치기</b>
</summary>
<div markdown="1">
![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)
</div>
</details>

## 4-6. 2차 액션 토픽 분석
<details>
<summary>
<b>2차 액션 토픽 분석 펼치기</b>
</summary>
<div markdown="1">
![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)
</div>
</details>

## 4-7. 페르소나 도출
<details>
<summary>
<b>페르소나 도출 펼치기</b>
</summary>
<div markdown="1">
![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)
</div>
</details>

</div>
</details>

## 5. ERD 다이어그램
![ERD Diagram](../assets/img/LightMe-ERDDiagram.png)

<br>

## 6. 핵심 기능
이 서비스의 핵심 기능은 나만의 감정 일기 작성입니다.
달력에 해당 날짜의 감정을 색깔로 표현하여 보여줍니다.

