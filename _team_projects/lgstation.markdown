---
layout: post
title: "LG Station"
permalink: /lgstation/
img: team_project/LG_LifeStation-thumbNail.png
date: 2024-12-05 00:00:00 +0900
description: (부트캠프 DX 프로젝트) 잠재 고객을 잡기위한 가전 체험 공간 솔루션
---

# :pushpin: LG Station
> 잠재 고객 확보를 위한 LG 가전 체험 공간 솔루션입니다. 편의점 관리를 위한 대시보드, 서비스 이용을 위한 결제 시스템, 고객 편의를 위한 어플리케이션으로 이루어져 있습니다.

<br>

## 1. 깃허브 링크
- [LgStation-Admin-FrontEnd](https://github.com/kimgusxo/dx_admin_dashboard_front){: target="_blank"}
- [LgStation-Admin-BackEnd](https://github.com/kimgusxo/DX_AdminDashBoard){: target="_blank"}
- [LgStation-Kiosk-FrontEnd](https://github.com/kimgusxo/dx_lg_life_station_app_webview){: target="_blank"}
- [LgStation-Kiosk-BackEnd](https://github.com/kimgusxo/DX_Kiosk){: target="_blank"}
- [LgStation-Application](https://github.com/kimgusxo/DX_Customer_App){: target="_blank"}

<br>

## 2. 제작 기간 & 참여 인원
- 2024년 11월 1일 ~ 2024년 12월 5일
- 팀 프로젝트
- 디자인 2명
  - 송정민(LG전자 DX School): 팀장, 문서 총괄 작성
  - 이예진(LG전자 DX School): 데이터 정리, 이미지 추출, 테스트 진행
- 기획 2명
  - 김주원(LG전자 DX School): 어플리케이션 디자인, 기능 설계, 피피티 작성
  - 이가현(LG전자 DX School): 발표자, BX, CX 전체 내용 작성
- 프론트엔드 1명
  - 이승현(LG전자 DX School): 데이터 크롤링, 프론트엔드 개발, 화면 설계
- 백엔드 & 클라이언트 1명
  - 김현태(LG전자 DX School): 백엔드 개발, 클라이언트 개발, 데이터베이스 설계, 데이터 분석

<br>

## 3. 기술 스택
### 3-1. Data Analyst 기술 스택
- Python
- BeautifulSoap
- Selenium
- Scipy
- Gensim

### 3-2. Front-End 기술 스택
- Vue.js
- Axios
- Pinia

### 3-3. Client-Side 기술 스택
- Dart
- Flutter
- Firebase

### 3-4 Back-End 기술 스택
- Java
- Spring Boot
- Spring Data Redis
- Spring Data Jpa
- Docker
- Swagger

### 3-5. Database 기술 스택
- PostgresSQL
- Redis
- Firestore

<br>

## 4. 데이터 분석
데이터 분석 과정은 20~30대는 1인 가구로 이루어져있어 "자취"라는 키워드에 여러 키워드를 붙여서 자취생활의 특징과 페인포인트를 잡아내고 클러스터링을 통해 특정 행동군에 집중하여 페르소나 도출

<details>
<summary><b>데이터 분석 과정 설명 펼치기</b></summary>
<div markdown="1">

### 4-1. 크롤링
<details>
<summary>
  <b>크롤링 상세 보기</b>
</summary>

<div markdown="1">

![Crawling](../assets/img/team_project/LG_LifeStation-Crawling.png)
- 더쿠/디시인사이드(자취/서브컬쳐/게임과 같은 20~30대가 주를 이루는 갤러리)에서 1차 키워드를 통해 넓은 범위의 크롤링 데이터를 얻고 Tf-idf를 통해 많이 나온 단어들을 통해 2차 크롤링을 진행하여 15,000개의 데이터 확보

</div>
</details>

### 4-2. 클러스터링
<details>

<summary>
  <b>클러스터링 상세 보기</b>
</summary>

<div markdown="1">

![Clustering1](../assets/img/team_project/LG_LifeStation-ClusteringPerformance.png)
- 계층적 클러스터링, K-Means, DBSCAN 방식으로 하이퍼 파라미터와 벡터화 방식을 바꿔서 덴드로그램과 실루엣지수를 뽑아봤지만 유의미한 계수(0.5 이상)가 나오지 않음, 가장 좋게 나온 벡터화 방식이 LDA 토픽 벡터로 도출

![Clustering2](../assets/img/team_project/LG_LifeStation-Clustering.png)
- LDA 토픽 벡터를 포함시켜 다시 클러스터링 성능평가를 한 결과 TfIdfVectorizer + LDA Topic Vecter + AgglomerativeClustering(ward 연결법)의 실루엣 지수와 클러스터링된 데이터의 균등한 분포를 확인하여 현 방식으로 진행

</div>
</details>

### 4-3. 토픽 분석 및 기회영역 분석
<details>

<summary>
  <b>토픽 분석 및 기회영역 분석 상세보기</b>
</summary>

<div markdown="1">

![ActorClustering](../assets/img/team_project/LG_LifeStation-ActorClustering.png)
- 클러스터링 된 데이터를 다시 LDA 토픽 모델링을 통해 액션을 도출하고 각각 내용을 분석

![Opportunity](../assets/img/team_project/LG_LifeStation-Opportunity.png)
- 모든 클러스터링의 모든 액션을 기회영역분석을 통해 그래프로 시각화하고 영역에 포진된 Actor2와 Actor4를 심층분석하여 중요 포인트 정리

</div>
</details>

### 4-3. 페르소나 도출
<details>

<summary>
  <b>페르소나 상세 보기</b>
</summary>

<div markdown="1">

![Persona](../assets/img/team_project/LG_LifeStation-Persona.png)
- 중요포인트를 토대로 페르소나 도출

</div>
</details>

</div>
</details>

<br>

## 5. 데이터베이스
### 5-1. ERD 다이어그램
![ERD](../assets/img/team_project/LG_LifeStation-ERD.png)

### 5-2. FireStore 컬렉션 구조
![FireStore](../assets/img/team_project/LG_LifeStation-FireStore.png)

### 5-3. Redis 키-값 쌍 구조
![Redis](../assets/img/team_project/LG_LifeStation-Redis.png)

<br>

## 6. 서비스 흐름도
### 6-1. 관리자 대시보드 흐름도
![ServiceFlow1](../assets/img/team_project/LG_LifeStation-ServiceFlow1.png)

### 6-2. 고객 어플리케이션 & 웹 결제 시스템 흐름도
![ServiceFlow2](../assets/img/team_project/LG_LifeStation-ServiceFlow2.png)

<br>

## 7. 시스템 아키텍쳐
![SystemArchitectuer](../assets/img/team_project/LG_LifeStation-SystemArchitecture.png)

<br>

## 8. 관리자 대시보드 핵심 기능

<details>
<summary><b>관리자 대시보드 기능 펼치기</b></summary>
<div markdown="1">

### 8-1. 메인 페이지
![DashBoard-Main](../assets/img/team_project/LG_LifeStation-DashBoardMain.png)
- 보고싶은 지점을 선택하고 해당 지점의 월 별 총 매출액, 월 별 매장 방문 고객 수, 월 별 밀키트 매출액 순위, 월 별 세탁용품 매출액 순위를 대시보드 형태로 보여준다.

### 8-2. 밀키트 페이지
![DashBoard-MealKit](../assets/img/team_project/LG_LifeStation-MealKit.png)
- 매장의 밀키트 리스트와 연도별 판매량 순위, 밀키트 별 판매량 차트, 월 별 밀키트 판매량 순위를 대시보드 형태로 보여준다.

### 8-3. 세탁용품 페이지
![DashBoard-Laundry](../assets/img/team_project/LG_LifeStation-Laundry.png)
- 매장의 세탁용품 리스트와 연도별 판매량 순위, 세탁용품 별 판매량 차트, 월 별 세탁용품 판매량 순위를 대시보드 형태로 보여준다.

### 8-4. 고객 페이지
![DashBoard-Customer](../assets/img/team_project/LG_LifeStation-Customer.png)
- 해당 매장을 방문한 고객 리스트와 성별/연령별 방문 고객 차트를 보여주고 성별/연령별 선호 밀키트 리스트를 대시보드 형태로 보여준다.

### 8-5. 가전 페이지
![DashBoard-HomeAppliance](../assets/img/team_project/LG_LifeStation-Appliance.png)
- 해당 매장에서 관리하고 있는 가전 리스트와 고장난 가전 리스트를 보여준다.

### 8-6. 재고 페이지
![DashBoard-Count](../assets/img/team_project/LG_LifeStation-Count.png)
- 재고가 20개 미만인 밀키트와 세탁용품을 보여주고 부족한 재고를 주문하는 기능을 한다.

</div>
</details>

<br>

## 9. 웹 결제 시스템 핵심 기능

<details>
<summary><b>웹 결제 시스템 기능 펼치기</b></summary>
<div markdown="1">

### 9-1. 이용권 페이지
![Kiosk-Ticket](../assets/img/team_project/LG_LifeStation-Ticket.png)
- 빨래를 위한 세탁/건조/스타일러/슈케어와 식사를 위한 주방 이용권을 구매하는 페이지이다.

### 9-2 상품 페이지
![Kiosk-Product](../assets/img/team_project/LG_LifeStation-Product.png)
- 상품을 주문할 수 있는 페이지이며 밀키트는 한식/중식/양식 카테고리로 나누어져있다.

### 9-2 담기 페이지
![Kiosk-ProductCount](../assets/img/team_project/LG_LifeStation-ProductCount.png)
- 구매할 상품의 개수를 설정하고 장바구니에 담는 페이지이다.

### 9-3. 장바구니 페이지
![Kiosk-ShopCart](../assets/img/team_project/LG_LifeStation-ShopCart.png)
- 담기 페이지를 통해 담은 상품들을 보여주는 페이지이다. 이용권을 구매한 고객은 10%의 할인율을 받는다.

### 9-4. 결제완료 페이지
![Kiosk-Complete](../assets/img/team_project/LG_LifeStation-Complete.png)
- 결제를 완료하면 카카오톡으로 QR코드를 보내주며 QR코드를 통해 상품을 수령할 수 있다.

</div>
</details>

<br>

## 10. 고객 어플리케이션 핵심 기능

<details>
<summary><b>고객 어플리케이션 기능 펼치기</b></summary>
<div markdown="1">

### 10-1. 로그인 화면
![App-Login](../assets/img/team_project/LG_LifeStation-Login.png)
- 카카오톡 로그인을 시작하는 페이지이다.

### 10-2. 카카오톡 로그인 화면
![App-KakaoLogin](../assets/img/team_project/LG_LifeStation-KakaoLogin.png)
- 카카오톡 아이디와 비밀번호를 통해 로그인한다.

### 10-3. 메인 화면
![App-Main](../assets/img/team_project/LG_LifeStation-AppMain.png)
- 모든 매장을 리스트 뷰 형태로 보여주며 터치를 통해 해당 매장의 웹 결제 시스템으로 이동할 수 있다.

### 10-4. 지도 화면
![App-Map](../assets/img/team_project/LG_LifeStation-Map.png)
- 매장의 위치를 마커로 지도에 표시해주며 마커를 터치하여 해당 매장의 웹 결제 시스템으로 이동할 수 있다.

### 10-5. 안내 화면
![App-Info](../assets/img/team_project/LG_LifeStation-Info.png)
- 해당 매장의 이용법들을 안내해주는 페이지이다.

### 10-6. 내 정보 화면
![App-MyInfo](../assets/img/team_project/LG_LifeStation-MyInfo.png)
- 정기권과 내가 구매한 내역들을 보여주는 페이지이다.

</div>
</details>

<br>

## 11. 문제점 회고
### 1. 실시간 동기화 문제
- 원인: Kiosk, 대시보드, 앱 등 여러 서비스에서 동일 데이터를 실시간으로 갱신해야 함.

- 원인분석: MQ(Kafka 등)도 고려했지만, Firestore가 클라이언트 연동과 실시간 이벤트 처리에 간단해 빠른 구현이 가능했음.

- 해결방안: Firestore 실시간 리스너와 낙관적 락(버전 필드) 적용으로 동시성 충돌을 최소화함.

### 2. 문제 2. Flutter 상태 관리
- 원인: Flutter 앱에서 WebView와 데이터를 주고받아야 하고, 이 과정에서 여러 화면이 동일한 정보를 공유해야 함.

- 원인분석: WebView 호출과 비동기 API 연동이 얽혀 단순 setState 방식으론 중복 상태가 많아지고, 화면 간 데이터 불일치가 빈번히 발생함.

- 해결방안: Provider 패턴을 도입해 전역 상태와 WebView 연동 로직을 일원화하고, 비동기 처리 결과도 자동으로 UI에 반영되도록 구조화함.

### 3. 재고 관리 문제
- 원인: 매일 0시에 재고를 일괄 갱신해야 하며, 수작업으로는 누락이나 지연이 빈번하게 발생함.

- 원인분석: 재고가 여러 서비스에서 동시 조회/수정되다 보니 시점별 재고 불일치 위험이 높았음.

- 해결방안: Spring Scheduler로 자정마다 자동 갱신하고, Firestore 트랜잭션 처리를 통해 일관성을 확보.