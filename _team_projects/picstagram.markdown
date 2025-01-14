---
layout: post
title:  "Picstagram"
permalink: /picstagram/
img: team_project/Picstagram-thumbNail.jpg
date: 2022-09-06 00:00:00 +0900
description: (교내프로젝트) 실시간 여행 공유 SNS 어플리케이션
---

# :pushpin: Picstagram
> 실시간 여행 공유 SNS 어플리케이션

<br>

## 1. 데모 링크
- [Picstagram](https://github.com/kimgusxo/Picstagram)

<br>

## 2. 제작 기간 & 참여 인원
- 2022년 9월 6일 ~ 2022년 12월 13일
- 팀 프로젝트
- Front-End 2명
    - 김동희(금오공과대학교): UI 구현 및 카메라, 사진, 게시물 기능 구현
    - 홍준표(금오공과대학교): 로그인 구현 및 팔로잉/팔로워 기능 구현

- Back-End 1명
    - 김현태(금오공과대학교): 데이터베이스 관리 및 백엔드 기능 구현

<br>

## 3. Back-End 사용 기술
- Javascript
- React Native
- Node.js
- Firebase Authentication
- Firebase FireStore

<br>

## 4. 데이터베이스 구조
![ERD Diagram](../assets/img/team_project/Picstagram-DBConstruct.png)

<br>

## 5. 화면 흐름도
![Page Flow](../assets/img/team_project/Picstagram-PageFlow.png)

<br> 

## 6. 핵심 기능
이 서비스의 핵심 기능은 사진 일기입니다.
사용자는 인앱 카메라로 사진을 찍거나 갤러리에 있는 사진을 통해
위치 좌표를 기준으로 지도에 여행 경로를 표시합니다.

<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">

### 6-1. 메인 화면
![MainPage](../assets/img/team_project/Picstagram-MainPage.png)

### 6-2. 지도 화면
![MapPage](../assets/img/team_project/Picstagram-MapPage.png)

### 6-3. 상세 게시물 화면
![PostPage](../assets/img/team_project/Picstagram-DetailPage.png)

### 6-4. 프로필 화면
![ProfilePage](../assets/img/team_project/Picstagram-Profile.png)

### 6-5. 팔로우/팔로잉
![FollowPage](../assets/img/team_project/Picstagram-Follow.png)

</div>
</details>

<br>

## 7. 시스템 아키텍쳐
![SystemArchitecture](../assets/img/team_project/Picstagram-SystemArchitecture.png)

<br>

## 8. 문제점 회고
### 1. 게시물(Post)·댓글(Comments) 삭제 시 하위 컬렉션 제거 문제
- 원인: Firestore에서 상위 문서(게시물) 삭제 시, 하위 컬렉션(댓글·이미지)이 자동으로 삭제되지 않음.

- 원인분석: Comments, Images 등 하위 컬렉션 문서를 모두 개별로 삭제 후에야 상위 문서를 완전히 제거할 수 있음.

- 해결방안: deleteCommentsByDocId(), deleteImagesByDocId() 등 유틸 함수를 만들어 하위 문서를 순차 삭제 후 상위 문서 삭제를 진행함.

### 2. Firestore 비동기 처리에서 forEach vs for ... of 사용 문제
- 원인: forEach 구문 안에서 async/await 사용 시, 순차적 처리가 보장되지 않음.

- 원인분석: forEach는 콜백 기반으로 병렬 실행되며, 레이스 컨디션이 발생할 수 있음.

- 해결방안: for ... of 구문으로 변경해, 비동기 로직을 직렬(순차) 처리하도록 개선함.