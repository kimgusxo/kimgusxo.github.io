---
layout: post
title: "PillGood"
permalink: /pillgood/
img: team_project/PillGood-thumbNail.jpg
date: 2023-03-06 00:00:00 +0900
description: (교내 프로젝트) OCR 기술을 활용한 처방전 기반 자동 복약관리 어플리케이션
---

# :pushpin: PillGood
> OCR 기술을 활용한 처방전 기반 자동 복약관리 어플리케이션

<br>

## 1. 깃허브 링크
- [PillGood-UI](https://www.figma.com/file/98GhZVArtu01389vLCcxB6/%ED%95%84%EA%B5%BF?type=design&node-id=0-1&mode=design){: target="_blank"}
- [PillGood](https://github.com/kimgusxo/pillgood){: target="_blank"}
- [PillGood-OCR](https://github.com/kimgusxo/pillgood-ocr){: target="_blank"}

<br>

## 2. 제작 기간 & 참여 인원
- 2023년 3월 6일 ~ 2023년 6월 14일
- 팀 프로젝트
- Front-End 2명
	- 김동희(금오공과대학교): REST API 구현, 카메라 기능 구현
	- 김주호(금오공과대학교): UI 구현, 데이터 수집 및 가공
- Back-End 2명
	- 김현준(금오공과대학교): 로그인 및 유저 관리, 자연어 처리, 예외처리 기능 구현
	- 김현태(금오공과대학교): 이미지 전처리 및 OCR 구현, 처방전 및 복약 관련 기능, 알림 기능 구현

<br>

## 3. Back-End 기술 스택
### Database Server
- Java 11
- Spring Boot 2.7.8
- Gradle
- Spring Data JPA
- MySQL
- Firebase Authentication
- Firebase Cloud Message

### Model Server 기술 스택
- Python 3.8
- Flask
- OpenCV
- EasyOCR
- Sklearn
- Pandas

<br>

## 4. ERD 다이어그램
![ERD Diagram](../assets/img/team_project/PillGood-ERDDiagram.png)

<br>

## 5. 핵심 기능
이 서비스의 핵심 기능은 처방전 OCR입니다.
사용자는 인앱 카메라로 처방전을 찍어 기본정보만 입력하고 전송하면 복약일정을 생성합니다.

<br>
 
<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">

## 5-2. FCM 전송
<video controls>
	<source src = "../assets/wav/PillGood-Notification.mp4" type = "video/mp4">
	동영상을 실행할 수 없습니다.
</video>
- 유저의 FCM 토큰을 통해 OCR이 완료됬다는 알림을 보냅니다.

## 5-3. 약 검색 동적쿼리
<video controls>
	<source src = "../assets/wav/PillGood-SearchingPill.mp4" type = "video/mp4">
	동영상을 실행할 수 없습니다.
</video>
- DTO에 저장된 값이 빈값 또는 Null값인지 확인하여 Criteria Interface 구현체를 통해 동적쿼리를 생성하여 해당 특징의 약을 검색합니다.

## 5-4. 이미지 전처리 및 OCR
<div style = "display: flex;">
	<img src="../assets/img/team_project/PillGood-OriginalImage.png" style = "flex: 1; width: 50%; height: auto;">
	<img src="../assets/img/team_project/PillGood-PreProcessImage.png" style = "flex: 1; width: 50%; height: auto;">
</div>
- 모델서버에서 이미지를 받게 되면 OpenCV를 사용하여 텍스트를 인식하기 쉽도록 텍스트 군집화를 통해 이미지를 자르고 이진화와 블러처리를 통해 OCR의 최적화된 이미지를 생성합니다.

</div>
</details>

<br>

## 6. 시스템 아키텍쳐
![ServiceArchitecture](../assets/img/team_project/PillGood-ServiceArchitecture.png)

<br>

## 8. 문제점 회고
### 1. 데이터 직렬화의 순환참조 문제
- 원인: JPA에서 양방향으로 연결된 Entity를 JSON으로 직렬화하는 과정에서 계속해서 참조하여 StackOverFlowError를 발생시키는 현상이다.

- 원인분석: DTO를 사용하여 통신하는데 DTO 내부에 필드인 객체가 Entity형태여서 문제가 발생한다는 것을 확인하였다.

- 해결방안: DTO에서 객체를 필드로 가지는 부분을 Long 타입의 외래키로 대체하였고 객체의 정보나 리스트의 타입이 Entity가 필요한 상황은 EntityConverter라는 Class를 만들고 전부 DTO로 변환하였다.

### 2. 모델서버를 두어야 하는가? 및 TessaractOCR의 한글인식률
- 원인: Java에서 지원하는 TessarectOCR과 OpenCV의 속도 및 정확도 측면에서 안좋은 성능을 보여주고 또한 알수없는 오류들이 발생하였다.

- 원인분석: Java의 Native method를 통해 라이브러리들이 구동되게 되는데 Native method를 사용하면 디버깅이 어렵고 성능도 낮게 나오는 것을 확인하였다.

- 해결방안: 다른 오픈소스 OCR인 EasyOCR을 사용할 수 있도록 파이썬의 Flask를 통해 Java SpringBoot와 OCR할 Image를 통신하였고 PreProcessing과 PostProcessing을 전부 진행 후 결과를 리턴받았다.

### 3. 카메라 밝기에 대한 OCR 결과와 이미지의 잡음 제거 문제점
- 원인: 같은 장소의 같은 환경에서 핸드폰 기종이 다르게 되면 OCR 결과가 유의미하게 달라지는 문제가 발생하였다.

- 원인분석: 회색조 영상으로 변환 후 밝기를 계산해보니 기종 별로 Image의 밝기 차이가 나는 것을 확인하였다.

- 해결방안: 가장 OCR 결과가 정확하게 나오는 구간(명도(130~170))을 계산하여 밝기 Processing을 하였다.