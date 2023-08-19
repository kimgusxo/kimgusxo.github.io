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
- Front-End 2명
	- 김동희(금오공과대학교): REST API 구현, 카메라 기능 구현
	- 김주호(금오공과대학교): UI 구현, 데이터 수집 및 가공
- Back-End 2명
	- 김현준(금오공과대학교): 로그인 및 유저 관리, 자연어 처리, 예외처리 기능 구현
	- 김현태(금오공과대학교): 이미지 전처리 및 OCR 구현, 처방전 및 복약 관련 기능, 알림 기능 구현

<br>

## 3. Back-End 사용 기술
### Database Server
	- Java 11
	- Spring Boot 2.7.8
	- Gradle
	- Spring Data JPA
	- MySQL
	- Firebase Authentication
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
- 데이터 서버: 그룹원, 약, 처방전, 복약, 복약 현황 기능 구현
	- 그룹원: 그룹원 생성, 수정, 삭제 구현
		<details>

		<summary>
		<b>코드 펼치기</b>
		</summary>

		<div markdown="1">

		![GroupMemberFunction](../assets/img/PillGood-GroupMemberFunctionCode.png)

		</div>
		</details>

	<br>

	- 약: 약이름을 통한 검색, 약특징을 통한 검색 구현	
		<details>
		
		<summary>
		<b>코드 펼치기</b>
		</summary>
		
		<div markdown="1">
		
		![PillFunction](../assets/img/PillGood-PillFunctionCode.png)
		
		</div>
		</details>

	<br>
	
	- 처방전: 처방전 등록, 수정, 삭제 구현
		<details>
		
		<summary>
		<b>코드 펼치기</b>
		</summary>
		
		<div markdown="1">
		
		![PrescriptionFunction](../assets/img/PillGood-PrescriptionFunctionCode.png)
		
		</div>
		</details>
	
	<br>

	- 복약: OCR 결과를 바탕으로 복약해야 할 약 검색 구현
		<details>
		
		<summary>
		<b>코드 펼치기</b>
		</summary>
		
		<div markdown="1">
		
		![TakePillFunction](../assets/img/PillGood-TakePillFunctionCode.png)
		
		</div>
		</details>

	<br>
	
	- 복약 현황: OCR 결과를 바탕으로 복약일정을 캘린더에 표시 및 설정한 시간이 되었을 때 알림 구현 
		<details>
		
		<summary>
		<b>코드 펼치기</b>
		</summary>
		
		<div markdown="1">
		
		![TakePillCheckFunction](../assets/img/PillGood-TakePillCheckFunctionCode.png)
		
		</div>
		</details>

<br>

- 모델 서버: 이미지 전처리, OCR 기능 구현
	- 이미지 전처리: GrayScale로 변환 후 밝기 조정, Image에 대한 Mopology 연산 및 텍스트 군집화로 이미지 resize 구현
		<details>
		
		<summary>
		<b>코드 펼치기</b>
		</summary>
		
		<div markdown="1">
		
		<div style = "display: flex;">
		<img src="../assets/img/PillGood-BlackBinary.png" style = "flex: 1; width: 50%; height: auto;">
		<img src="../assets/img/PillGood-WhiteBinary.png" style = "flex: 1; width: 50%; height: auto;">
		</div>

		<br>

		<div style = "display: flex;">
		<img src="../assets/img/PillGood-BrightnessCode.png" style = "flex: 1; width: 50%; height: auto;">
		<img src="../assets/img/PillGood-CroppedImage.png" style = "flex: 1; width: 50%; height: auto;">
		</div>

		</div>
		</details>

	<br>

	- OCR: EasyOCR을 사용하여 OCR기능 구현 및 Regular Expression으로 필요한 기본데이터 처리 구현
		<details>
		
		<summary>
		<b>코드 펼치기</b>
		</summary>
		
		<div markdown="1">
		
		![PillFunction](../assets/img/PillGood-OCR.png)
		
		</div>
		</details>

<br>

## 7. 문제점 회고
#### 1. 데이터 직렬화의 순환참조 문제
- 원인: JPA에서 양방향으로 연결된 Entity를 JSON으로 직렬화하는 과정에서 계속해서 참조하여 StackOverFlowError를 발생시키는 현상이다.

- 원인분석: DTO를 사용하여 통신하는데 DTO 내부에 필드인 객체가 Entity형태여서 문제가 발생한다는 것을 확인하였다.

- 해결방안: DTO에서 객체를 필드로 가지는 부분을 Long 타입의 외래키로 대체하였고 객체의 정보나 리스트의 타입이 Entity가 필요한 상황은 EntityConverter라는 Class를 만들고 전부 DTO로 변환하였다.

#### 2. 모델서버를 두어야 하는가? 및 TessaractOCR의 한글인식률
- 원인: Java에서 지원하는 TessarectOCR과 OpenCV의 속도 및 정확도 측면에서 안좋은 성능을 보여주고 또한 알수없는 오류들이 발생하였다.

- 원인분석: Java의 Native method를 통해 라이브러리들이 구동되게 되는데 Native method를 사용하면 디버깅이 어렵고 성능도 낮게 나오는 것을 확인하였다.

- 해결방안: 다른 오픈소스 OCR인 EasyOCR을 사용할 수 있도록 파이썬의 Flask를 통해 Java SpringBoot와 OCR할 Image를 통신하였고 PreProcessing과 PostProcessing을 전부 진행 후 결과를 리턴받았다.

#### 3. 카메라 밝기에 대한 OCR 결과와 이미지의 잡음 제거 문제점
- 원인: 같은 장소의 같은 환경에서 핸드폰 기종이 다르게 되면 OCR 결과가 유의미하게 달라지는 문제가 발생하였다.

- 원인분석: 회색조 영상으로 변환 후 밝기를 계산해보니 기종 별로 Image의 밝기 차이가 나는 것을 확인하였다.

- 해결방안: 가장 OCR 결과가 정확하게 나오는 구간(명도(130~170))을 계산하여 밝기 Processing을 하였다.