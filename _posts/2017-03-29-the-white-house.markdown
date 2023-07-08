---
layout: post
title:  "PillGood"
img: PillGood-thumbNail.jpg
date:   2023-03-06 00:00:00 +0900
description: OCR 기술을 활용한 처방전 기반 자동 복약관리 어플리케이션
---

# :pushpin: PillGood
> OCR 기술을 활용한 처방전 기반 자동 복약관리 어플리케이션

<br>

## 1. 데모 링크
- [PillGood](https://github.com/kimgusxo/pillgood)

<br>

## 2. 제작 기간 & 참여 인원
- 2023년 3월 6일 ~ 2023년 6월 14일
- 팀 프로젝트
- Front-End 2명, Back-End 2명

<br>

## 3. Back-End 사용 기술
### Database Server
	- Java 11
	- Spring Boot 2.7.8
	- Gradle
	- Spring Data JPA
	- MySQL
	- Firebase Authentocation
	- Firebase Cloud Message

### Model Server
	- Python 3.8
	- Flask
	- OpenCV
	- EasyOCR
	- Sklearn
	- Pandas

<br>

## 4. ERD 다이어그램
![ERD Diagram](../assets/img/PillGood-ERDDiagram.png)

<br>

## 5. 핵심 기능
이 서비스의 핵심 기능은 처방전 OCR입니다.
사용자는 인앱 카메라로 처방전을 찍어 기본정보만 입력하고 전송하면 복약일정을 생성합니다.

<br>
 
<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">

## 5.1. Controller
### OCR 모델서버로 이미지 전송
![sendImage](../assets/img/PillGood-SendImage.png)
- Controller에서는 MultiPartFile로 이미지를 전달받고 OCR 모델서버로 이미지를 전송합니다. 그 후 전송된 이미지의 OCR 결과를 받고 정보를 추가하여 사용자에게 응답합니다.

## 5.2. Service
### FCM 전송
<video controls>
	<source src = "../assets/wav/PillGood-Notification.mp4" type = "video/mp4">
	동영상을 실행할 수 없습니다.
</video>
- 유저의 FCM 토큰을 통해 OCR이 완료됬다는 알림을 보냅니다.

## 5.3. Repository
### 약 검색 동적쿼리
<video controls>
	<source src = "../assets/wav/PillGood-SearchingPill.mp4" type = "video/mp4">
	동영상을 실행할 수 없습니다.
</video>
- DTO에 저장된 값이 빈값 또는 Null값인지 확인하여 Criteria Interface 구현체를 통해 동적쿼리를 생성하여 해당 특징의 약을 검색합니다.

## 5.4. OCR
### 이미지 전처리
<div style = "display: flex;">
	<img src="../assets/img/PillGood-OriginalImage.png" style = "flex: 1; width: 50%; height: auto;">
	<img src="../assets/img/PillGood-PreProcessImage.png" style = "flex: 1; width: 50%; height: auto;">
</div>
- 모델서버에서 이미지를 받게 되면 OpenCV를 사용하여 텍스트를 인식하기 쉽도록 텍스트 군집화를 통해 이미지를 자르고 이진화와 블러처리를 통해 OCR의 최적화된 이미지를 생성합니다.

</div>
</details>

<br>

## 5. 서비스 아키텍쳐
![ServiceArchitecture](../assets/img/PillGood-ServiceArchitecture.png)

<br>

## 6. 코드 파트 및 구현 이유
- 그룹원, 약, 처방전, 복약, 복약현황
- 이미지 전처리, OCR

<br>

## 7. 트러블 슈팅
- None

<br>

## 8. 회고
