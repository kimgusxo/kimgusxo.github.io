---
layout: post
title: "Library"
permalink: /library/
img: team_project/LibraryCompetition-thumbNail.png
date: 2024-08-30 00:00:00 +0900
description: (국립 중앙도서관 아이디어 공모전) 도서 훼손 판독을 통한 대시보드 어플리케이션
---

# :pushpin: LibraryCompetition
> OpenCV를 활용한 도서 훼손 판독 대시보드 어플리케이션

<br>

## 1. 깃허브 링크
- [LibraryCompetition-FrontEnd](https://github.com/kimgusxo/LibraryCompetition){: target="_blank"}
- [LibraryCompetition-Backend](https://github.com/kimgusxo/LibraryCompetition){: target="_blank"}

<br>

## 2. 제작 기간 & 참여 인원
- 2024년 7월 29일 ~ 2024년 8월 29일
- 팀 프로젝트
- Front-End 2명
    - 이승현(LG전자 DX School): UI/UX, 대시보드 구현
    - 정다진(LG전자 DX School): REST API 구현
- Back-End 1명
    - 김현태(LG전자 DX School): REST API 구현, 백엔드 구현
- Image-Server 1명
    - 이성찬(LG전자 DX School): 도서 훼손도 분석 구현

<br>

## 3. Back-End 기술 스택
- Java 17
- Spring Boot 3.3.2
- Gradle
- Spring Data JPA
- MongoDB
- Swagger

<br>

## 4. 어플리케이션 개발 이유
![Graph](../assets/img/team_project/LibraryCompetition-Graph.png)
- 훼손/분실로 폐기되는 도서들이 증가하고 있고 책의 재구매를 위해 일정비용 이상 지출중임.

<br>

## 5. Document 구조
![Document](../assets/img/team_project/LibraryCompetition-Document.png)

<br>

## 6. 핵심 기능
이 서비스의 핵심 기능은 도서 훼손 판독입니다.
단말기 카메라가 3방향에서 도서 이미지를 생성하면 훼손도를 판독하여 대시보드를 갱신합니다.

<br>

<details>

<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">

### 6-1. 도서관 도서 검색 페이지
<details>

<summary>
  <b>도서관 도서 검색 페이지 보기</b>
</summary>

<div markdown="1">

![BookSearchPage]()

</div>
</details>

### 6-2. 도서관 사용자 검색 페이지
<details>

<summary>
  <b>도서관 사용자 검색 페이지 보기</b>
</summary>

<div markdown="1">

![UserSearchPage]()

</div>
</details>

### 6-3. 도서 상세정보 페이지
<details>

<summary>
  <b>도서 상세정보 페이지 보기</b>
</summary>

<div markdown="1">

![BookDetailPage]()

</div>
</details>

### 6-4. 사용자 상세 정보 페이지
<details>

<summary>
  <b>사용자 상세 정보 페이지 보기</b>
</summary>

<div markdown="1">

![UserDetailPage]()

</div>
</details>

### 6-5. 도서 이미지 훼손도 분석 페이지
<details>

<summary>
  <b>도서 이미지 훼손도 분석 페이지 보기</b>
</summary>

<div markdown="1">

![DamageDetectPage]()

</div>
</details>

### 6-6. 도서 이미지 훼손도 분석
<details>

<summary>
  <b>도서 이미지 훼손도 분석 보기</b>
</summary>

<div markdown="1">

![DamageDetect]()

</div>
</details>

</div>
</details>

<br>

## 7. 단말기 설계도
![MachineArchitecture]()

<br>

## 8. 문제점 회고
### 1. 