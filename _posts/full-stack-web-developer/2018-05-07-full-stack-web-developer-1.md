---
layout: post
title: "Full-Stack Web Developer되기 - 1"
description: "부스트코스의 Full-Stack Web Developer 강좌를 보며 정리한 내용입니다."
tags: [full-stack, web developer]
published: false
comments: true
image:
  feature: full-stack-web-developer.png
---

---
## <span style="color:blue">1. 웹 프로그래밍 기초</span>
### (1) Web 개발의 이해 - FE/BE
1. 웹 관련 인기 언어
    - Python: 읽기 쉽고 적은 코드로 프로그램 개발 가능, 입문자에게 좋음
    - PHP: 웹의 80% 이상이 PHP, 웹 개발에 많이 사용
    - JavaScript: 프론트 개발자라면 반드시 알아야 할 언어
    - JAVA: 큰 규모 소프트웨어 개발에 자바언어 많이 사용
    - Ruby: 빠른 개발에 사용, 단순하고 세련된 웹 앱으로 인기있는 언어

2. 웹의 동작(HTTP 프로토콜 이해)
    1. HTTP(Hypertext Transfer Protocol)이란?
        - 팀 버너스리의 팀이 웹 브라우저, 관련 기술과 함께 발명
        - Server와 Client가 인터넷상에서 데이터를 주고받기 위한 프로토콜
    2. HTTP 작동 방식
        - HTTP는 서버/클라이언트 모델
        - 장점
          - 불특정 다수 대상 서비스
          - 클라이언트보다 많은 요청과 응답 처리 가능
        - 단점
          - Stateless(무상태) 특징: 연결 끊음(클라이언트 상태 모름)
          - 잇따라 Cookie 기술 등장
    3. URL(Uniform Resource Locator)
        - 인터넷 웹 상의 자원 위치 나타냄
        - 접근 프로토콜://IP주소 또는 도메인 이름/문서의 경로/문서 이름
        - ex) http://www.sunnyvale.co.kr/docs/index.html
        <img src="/images/full-stack-web-developer/full-stack-web-developer-1.png" alt="" />
        - 요청 메서드 : GET, PUT, POST, PUSH, OPTIONS 등의 요청 방식이 온다.
          - GET : 정보를 요청하기 위해서 사용한다. (SELECT)(요청 body 없음)
          - POST : 정보를 밀어넣기 위해서 사용한다. (INSERT)
        - 요청 URI : 요청하는 자원의 위치를 명시한다.
        - HTTP 프로토콜 버전 : 웹 브라우저가 사용하는 프로토콜 버전이다.

3. 웹 Front-End 와 웹 Back-End
    - 웹은 프론트엔드(FE)와 백엔드(BE)로 나눠짐
    - Web Front-End란?
      - 사용자에게 웹을 통해 다양한 콘텐츠(문서, 영상, 사진 등)를 제공
      - 사용자의 요청에 반응하여 동작
      - Role
        - HTML: 웹 콘텐츠 잘 보여주기 위한 구조 제작(신문, 책 등)
        - CSS: 적절한 배와 일관된 디자인 제공(보기 좋게)
        - Javascript: 사용자 요청 잘 반영(소통하듯이)
    - Web Back-End란?
      - (Server Side 개발) <-> Front-End (Client Side 개발)
      - 정보 처리 저장, 요청에 따른 정보 내려주는 역할
      - 상품 정보, 주문 받아 저장, 사용자 관심있는 상품 골라줌
      - Back-End 개발자 알아야 할 것들
        - 프로그래밍 언어(JAVA, Python, PHP, Javascript 등)
        - 웹의 동작 원리
        - 알고리즘, 자료구조 등 프로그래밍 기반 지식
        - 운영체제, 네트워크 등에 대한 이해
        - 프레임워크에 대한 이해(Spring 등)
        - DBMS에 대한 이해와 사용방법(MySQL, Oracle 등)

4. browser의 동작
    - Browser란?
      - 서버에서 전송한 데이터(HTML과 같은)가 클라이언트에 도착해야할 곳
      - Parser: 데이터 해석
      - Rendering Engine: 데이터를 화면해 표현
    - Webkit 렌더링엔진의 처리과정
    <img src="/images/full-stack-web-developer/webkitflow.png" alt="" />
      - Parser: HTML, CSS -> DOM Tree, CSS Tree 만듦
      - Render Tree: DOM Tree과 CSS Tree를 조합
      - Painting: Render Tree 정보를 통해 화면의 해당 부분에 칠하는 과정

5. browser에서의 웹 개발
    - [웹에서 html, css, javascript 테스트 웹사이트](http://jsbin.com/?html,output)

6. 웹서버
    - 웹서버란?
      - 웹 서버 소프트웨어 혹은 웹 서버 소프트웨어가 동작하는 컴퓨터
      - Client가 요청하는 HTML문서나 각종 리소스(Resource)를 전달하는 것
    - 웹 서버 소프트웨어의 종류
      - Apache, Nginx, Microsoft, Google 웹 서버

7. WAS(Web Application Server)
    - 클라이언트/서버 구조
      - Client는 Service를 제공하는 Server에게 정보를 요청하여 응답 받은 결과 사용
    - DBMS(Database Management System)
      - 다수의 사용자가 DB내의 데이터에 접근할 수 있도록 해주는 소프트웨어
      - Client에 비즈니스 로직이 많을 경우 Client 관리(배포 등)비용 문제
    - 미들웨어(MiddleWare)
      - Client에 비즈니스 로직이 많을 경우 Client 관리(배포 등)비용 문제 해결 방안
      - 또 다른 미들웨어 서버에서 비즈니스 로직 동작 => Client는 입출력만 담당
      <img src="/images/full-stack-web-developer/middleware.png" alt="" />
    - WAS(Web Application Server)
      - 일종의 미들웨어로 웹 Client의 요청 중 웹 앱이 동작하도록 지원
      - 웹 서버 vs WAS
        - WAS도 보통 자체적 웹 서버 기능 내장
        - 규모가 커질수록 웹 서버와 WAS 분리(유지보수 위해)
        - WAS 터질 경우 임시적으로 Web Server 사용하는 등으로 이용
        <img src="/images/full-stack-web-developer/WAS.png" alt="" />

---
### (2) HTML - FE
1. HTML Tags
    - 태그의 종류
      - anchor(링크)
      - img(이미지)
      - ul/li(목록)
      - heading(제목)
      - p(문단)
      - div(block element)

2. HTML Layout Tag(배치 태그)
    - header
    - section
    - nav
    - footer
    - aside
    <img src="images/full-stack-web-developer/HTML5PageLayout.jpg" alt="" />

3. HTML 구조설계

4. class와 id 속성



---
### (3) CSS - FE


---
### (4) 개발환경 설정 - BE


---
### (5) Servlet - BE


---
### (6) Summary




---
## 참조
  * [부스트 코스 강의](http://www.edwith.org/boostcourse-web)
