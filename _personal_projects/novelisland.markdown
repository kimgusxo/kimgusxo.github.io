---
layout: post
title:  "NovelIsland"
permalink: /novelisland/
img: NovelIsland-thumbNail.png
date: 2023-12-06 00:00:00 +0900
description: (엘라스틱서치와 배포 공부용) 문장형 소설 검색 엔진 사이트
---

# :pushpin: NovelIsland
> 웹소설을 문장형으로 검색하여 저장하고 찾는 어플리케이션

<br>

## 1. 깃허브 링크
- [NovelIsland-Crawling](https://github.com/kimgusxo/NovelIsland-Crawling){: target="_blank"}
- [NovelIsland-FrontEnd](https://github.com/kimgusxo/NovelIsland-FrontEnd){: target="_blank"}
- [NovelIsland-BackEnd](https://github.com/kimgusxo/NovelIsland-BackEnd){: target="_blank"}

<br>

## 2. 제작 기간 & 참여 인원
- 2023년 10월 1일 ~ 2023년 12월 06일
- 개인프로젝트
- Front-End & Back-End
  - 김현태(금오공과대학교)

<br>

## 3-1. Front-End 기술 스택
- JavaScript
- HTML
- CSS
- Vue.js
- Vuex
- Vue-Router
- Axios

## 3-2. Back-End 기술 스택
- Java 11
- Spring Boot 2.7.10
- Spring Data JPA
- PostgreSQL 15
- ElasticSearch 7.17.9
- Gradle
- Spring Security
- Spring Batch
- Spring Test

## 3-3. 데이터 수집 기술 스택
- Python 3.8
- BeautifulSoap
- Selenium

## 3-4. 배포 및 호스팅 기술 스택
- GitHub Page
- GitHub Actions
- Docker
- Docker Hub
- Docker Compose
- AWS EC2
- AWS S3
- Certbot

<br>

## 4. ERD 다이어그램
![ERD Diagram](../assets/img/personal_project/NovelIsland-ERDDiagram.png)

<br>

## 5. 핵심 기능
이 서비스의 핵심 기능은 소설 검색과 북마크입니다.
찾고 싶은 소설을 검색하고 상세 설명을 보며 마음에 든다면 북마크하여 볼 소설들을 기록할 수 있습니다.

<br>

<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">

## 5-1. 소설 검색
<details>

<summary>
  <b>소설 검색 보기</b>
</summary>
		
<div markdown="1">
		
![NovelSearch](../assets/img/personal_project/NovelIsland-NovelSearch.png)
		
</div>
</details>

## 5-2. 작가 검색

<details>

<summary>
  <b>작가 검색 보기</b>
</summary>

<div markdown="1">

![AuthorSearch](../assets/img/personal_project/NovelIsland-AuthorSearch.png)

</div>
</details>

## 5-3. 장르 검색

<details>

<summary>
  <b>장르 검색 보기</b>
</summary>

<div markdown="1">

![GenreSearch](../assets/img/personal_project/NovelIsland-GenreSearch.png)

</div>
</details>

## 5-4. 북마크 관리

<details>

<summary>
  <b>북마크 관리 보기</b>
</summary>

<div markdown="1">

![Bookmark1](../assets/img/personal_project/NovelIsland-Bookmark1.png)
![Bookmark2](../assets/img/personal_project/NovelIsland-Bookmark2.png)

</div>
</details>

## 5-5. 북마크 등록

<details>

<summary>
  <b>북마크 등록 보기</b>
</summary>

<div markdown="1">

![BookmarkRegistration1](../assets/img/personal_project/NovelIsland-BookmarkRegistration1.png)
![BookmarkRegistration1](../assets/img/personal_project/NovelIsland-BookmarkRegistration2.png)
</div>
</details>

## 5-6. 북마크 해제

<details>

<summary>
  <b>북마크 해제 펼치기</b>
</summary>

<div markdown="1">

![BookmarkClear1](../assets/img/personal_project/NovelIsland-BookmarkClear1.png)
![BookmarkClear2](../assets/img/personal_project/NovelIsland-BookmarkClear2.png)

</div>
</details>

## 5-7. 문장형 소설 검색

<details>

<summary>
  <b>문장형 소설 검색 보기</b>
</summary>

<div markdown="1">

![SentenceSearch1](../assets/img/personal_project/NovelIsland-SentenceSearch1.png)
![SentenceSearch2](../assets/img/personal_project/NovelIsland-SentenceSearch2.png)

</div>
</details>

## 5-8. 소설 상세정보

<details>

<summary>
  <b>소설 상세정보 보기</b>
</summary>

<div markdown="1">

![NovelDescription](../assets/img/personal_project/NovelIsland-NovelDescription.png)

</div>
</details>

## 5-9. 웹소설 데이터 크롤링

<details>

<summary>
  <b>데이터 크롤링 보기</b>
</summary>

<div markdown="1">



</div>
</details>

</div>
</details>

<br>

## 6. 배치 다이어그램
![BatchDiagram](../assets/img/personal_project/NovelIsland-BatchDiagram.png)

<br>

## 7. 스프링 사용 기술 코드
- 백엔드 서버: Spring Test, Spring Batch, Spring Security
- Spring Test(Controller, Service, Repository 단위 테스트)
  <details>

  <summary>
  <b>코드 펼치기</b>
  </summary>

  <div markdown="1">



  </div>
  </details>
- Spring Test(통합 테스트)
  <details>

  <summary>
    <b>코드 펼치기</b>
  </summary>

  <div markdown="1">



  </div>
  </details>

- Spring Batch
  <details>

  <summary>
    <b>코드 펼치기</b>
  </summary>

  <div markdown="1">



  </div>
  </details>

- Spring Security
  <details>

  <summary>
    <b>코드 펼치기</b>
  </summary>

  <div markdown="1">



  </div>
  </details>

<br>

## 8. 문제점 회고
### 1. Service Layer 단위 테스트 시 의존성 제거 문제점
- 원인: Service 계층의 단위 테스트를 작성하는데 Controller와 Repository와의 의존을 제거해 Layer의 단위 테스트가 가능하다고 판단하였다.

- 원인분석: given을 통해 Controller의 인자를 제공하고 when을 통해 Repository의 반환값을 설정하여 Service 계층의 Business Logic만 테스트 할 수 있도록 설정하였다.

- 해결방안: Mockito와 라이브러리와 Mock을 사용하여 의존성을 제거하여 Service 계층만 테스트를 진행하였다.

### 2. Spring Batch를 사용하여 DB에 데이터를 삽입할 때 중복을 제거해야 하는 문제점
- 원인: 크롤링한 CSV 데이터와 데이터베이스 테이블의 필드가 일치하지 않아 문제가 발생하는 현상이다.

- 원인분석: Primary Key인 필드를 넣기 위해 중복을 제거한 리스트가 필요한 것을 확인하였다.

- 해결방안: 중복을 제거하는 Utility를 작성하여 리스트 안의 데이터를 가공하여 삽입하였다.

<br>

## 9. 트러블 슈팅
### 1. 멀티 쓰레드에서 동시에 회원가입을 할 때 아이디가 중복으로 회원가입 되는 현상
- 문제점 분석: 서비스 도중 에러 로그를 확인했더니 같은 아이디로 중복 회원가입이 되어 유저 아이디로 요청하는 모든 요청이 에러가 발생함.

- 해결방안:  @Lock, @Version으로 락을 걸 경우 Database에 존재하지 않기 때문에 ReentrantLock을 사용하여 userId에 대한 락을 걸어 하나의 요청만 회원가입 시키도록 해결하였다.