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
- [LibraryCompetition-FrontEnd](https://github.com/kimgusxo/LibraryCompetition-Frontend){: target="_blank"}
- [LibraryCompetition-Backend](https://github.com/kimgusxo/LibraryCompetition-Backend){: target="_blank"}
- [LibraryCompetition-Model](https://github.com/kimgusxo/LibraryCompetition-Model){: target="_blank"}

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
![Document](../assets/img/team_project/LibraryCompetition-ERDDiagram.png)

<br>

## 6. 시스템 아키텍쳐
![SystemArchitecture](../assets/img/team_project/LibraryCompetition-SystemArchitecture.png)

<br>

## 7. 핵심 기능
이 서비스의 핵심 기능은 도서 훼손 판독입니다.
단말기 카메라가 3방향에서 도서 이미지를 생성하면 훼손도를 판독하여 대시보드를 갱신합니다.

<details>

<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">

### 7-1. 도서관 도서 검색 페이지
<details>

<summary>
  <b>도서관 도서 검색 페이지 보기</b>
</summary>

<div markdown="1">

![BookPage](../assets/img/team_project/LibraryCompetition-BookPage.png)
- 해당 도서관의 도서 목록과 상태를 대시보드 형태로 보여준다.

</div>
</details>

### 7-2. 도서관 사용자 검색 페이지
<details>

<summary>
  <b>도서관 사용자 검색 페이지 보기</b>
</summary>

<div markdown="1">

![MemberPage](../assets/img/team_project/LibraryCompetition-MemberPage.png)
- 해당 도서관의 이용자 목록과 상태를 대시보드 형태로 보여준다.

</div>
</details>

### 7-3. 도서 상세정보 페이지
<details>

<summary>
  <b>도서 상세정보 페이지 보기</b>
</summary>

<div markdown="1">

![BookDetail](../assets/img/team_project/LibraryCompetition-BookDetail.png)
- 해당 도서의 기본정보와 훼손률, 대출기록을 확인할 수 있다.

</div>
</details>

### 7-4. 사용자 상세 정보 페이지
<details>

<summary>
  <b>사용자 상세 정보 페이지 보기</b>
</summary>

<div markdown="1">

![MemberDetail](../assets/img/team_project/LibraryCompetition-MemberDetail.png)
- 해당 유저의 대출 기록과 훼손 기록을 볼 수 있다.

</div>
</details>

### 7-5. 도서 이미지 훼손도 판단 페이지
<details>

<summary>
  <b>도서 이미지 훼손도 분석 페이지 보기</b>
</summary>

<div markdown="1">

![ImagePage](../assets/img/team_project/LibraryCompetition-ImagePage.png)
- 반납 시 3방향(정면, 우상단, 좌하단)의 사진을 통해 훼손률을 확인할 수 있다.

</div>
</details>

### 7-6. 도서 이미지 훼손도 분석
<details>

<summary>
  <b>도서 이미지 훼손도 분석 보기</b>
</summary>

<div markdown="1">

![Result](../assets/img/team_project/LibraryCompetition-Result.png)
- 훼손도 판독 모델을 사용하여 9방향의 그리드를 통해 구역별로 훼손도를 측정하여 사용자가 훼손을 시켰는지 판단한다.

</div>
</details>

</div>
</details>

<br>

## 8. 문제점 회고
### 1. 이미지 정렬 및 보정 알고리즘의 한계
- 원인: 단말기에서 촬영된 도서 이미지의 각도나 조명, 노이즈 등의 차이로 인해, OpenCV 기반 ORB를 활용한 이미지 정렬 및 Farneback Optical Flow 보정이 다양한 환경에서 일관된 결과를 내기 어려웠습니다.

- 원인분석: ORB 디텍터로 추출한 특징점이 촬영 조건에 따라 불안정하게 검출되어 정렬 시 오차가 발생하였으며, Optical Flow 기반 보정 과정에서는 이미지 간 미세한 차이가 큰 보정 오차로 이어져 후속 차이 이미지 및 훼손 영역 검출에 부정적인 영향을 미치는 사례가 발견되었습니다.

- 해결방안: 다양한 촬영 조건에 대응할 수 있도록 전처리 모듈을 보완하고, 필요 시 SIFT나 SURF와 같은 대체 알고리즘을 테스트하여 적용하며, 이미지 정렬 및 보정 결과에 대해 임계값 조정과 후처리 보정 단계를 추가하여 결과의 일관성을 확보하도록 개선하였습니다.

### 2. 파일 준비 및 동기화 문제
- 원인: Watchdog를 이용해 src 폴더와 src_diff 폴더의 파일 변경 사항을 모니터링하는 과정에서, 두 이미지가 완전히 기록되기 전에 처리되는 경우가 발생하여 불완전한 파일이 처리되는 문제가 있었습니다.

- 원인분석: 파일이 완전히 업로드되기 전에 단순 크기 검사로 안정성을 판단함으로써 불완전한 파일이 처리되는 사례가 있었고, src와 src_diff 폴더의 파일 업로드 타이밍이 상이하여 한쪽 파일만 준비된 상태에서 처리 로직이 동작하는 문제가 나타났습니다.

- 해결방안: 파일의 최종 수정 시간(mtime)이나 파일 잠금 상태를 추가로 확인하여 안정적인 파일 준비 여부를 확정하고, 두 이미지 파일이 모두 준비되었을 때만 처리되도록 별도 큐나 동기화 객체를 활용하는 등 동기화 로직을 보완하여 문제를 개선하였습니다.