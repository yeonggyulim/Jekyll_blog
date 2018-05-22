---
layout: post
title: "Full-Stack Web Developer되기 - 1"
description: "부스트코스의 Full-Stack Web Developer 강좌를 보며 정리한 내용입니다."
tags: [full-stack, web developer]
published: true
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
    - [온라인으로 html,css 만들고 공유하기](https://codepen.io/)

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

3. class와 id 속성
    - ID(Identifier)
      - 고유한 속성, HTML문서에 하나만 사용
      - ID를 통해 검색에 용이
    - Class
      - HTML문서에 중복해서 사용
      - 한 태그에 여러 개의 class 사용 가능(공백으로 구분)
      - 홈페이지의 일관성 위한 속성

---
### (3) CSS - FE
1. CSS 선언 방법
    - CSS의 구성
    ```css
      span{
        color: blue;
      }
    ```
      - `span`: selector
      - `color`: property
      - `blue`: value
    - HTML에 style 적용하는 3가지 방법
      - Inline
        - HTML 태그 내에 적용
        - 모든 방법 중 가장 우선으로 적용
      - Internal
        - Style 태그로 지정
        - 구조와 스타일 섞이므로 유지보수 어렵
        - 브라우저가 서버에 별도의 CSS 파일 요청 필요 X
      - External
        - 외부파일(.css)로 지정
        - CSS가 짧지 않다면 가장 추천하는 방법

2. 상속과 우선순위 결정
    - box-model 속성(width, height, margin, padding, border)과 같은 크기 배치 속성 제외
    - 보통 속성들은 div에 style주면 div안의 모든 태그에 상속되어 속성 적용

3. CSS Selector
    - element에 style 지정 위한 3가지 기본 선택자
      - tag로 지정
      ```css
       span {
         color : red;
       }
      ```

      - id로 지정
      ```css
        #spantag {
          color : red;
        }
      ```

      - class로 지정
      ```css
        .spanClass {
          color : red
        }
      ```
    - id, class 요소 선택자 활용
    ```css
    #myid { color : red }
    div.myclassname { color : red }
    ```
    - 그룹 선택
    ```css
    h1, span, div { color : red }
    h1, span, div#id { color : red }
    h1.span, div.classname { color : red }
    ```
    - 자손 선택(공백): 요소 선택(아래 모든 span 태그)
    ```css
    #jisu span { color : red }
    ```
    - 자식 선택(>): 바로 하위엘리먼트 선택(jisu바로 아래 span 태그)
    ```css
    #jisu > span { color : red }
    ```

4. Element가 배치되는 방법(CSS Layout)
    - layout 작업(Rendering 과정): 엘리먼트 화면에 배치하는 것
    - 위에서 아래로 블럭 이루며 배치되는 것이 기본
    - CSS는 이외에도 다양한 배치를 위한 추가적인 속성 제공
    - 중요한 배치 속성들
      - display(block, inline, inline-block)
        - `display: block` - 벽돌 쌓듯이 아래로 블록이 쌓임
        - `display: inline` - 좌측에서 우측으로 먼저 흐름(높이와 넓이 반영 X)
      - position(static, absolute, relative, fixed)
        - `static` - default 속성(순서대로 배치)
        - `absolute` - t/l/r/b으로 설정, 기준점(상위엘리먼트 중 static이 아닌 position)을 기준으로 이동
        - `relative` - t/l/r/b으로 설정, 원래 자신 위치할 곳 기준으로 이동
        - `fixed`- viewport(전체화면) 좌측, 맨 위를 기준으로 동작
      - float(left, right)
        - 기존의 배치에서 벗어난 예외적인 배치
    - 하나의 블록 element는 box model 형태
    - element의 default 크기는 부모의 크기
    - box-sizing
      - `content-box` - default 속성(padding에 의해 크기 커짐)
      - `border-box` - padding 늘려도 박스 크기 고정(제한 있음)

5. float 기반 샘플 화면 레이아웃 구성
    - 가운데 main contents를 `float:left`로 정렬시키는 레이아웃
    - footer: `clear:both` - 왼쪽, 오른쪽 float 모두 인식
    - 상위 element: `overflow:auto` - float를 부모입장에서 인식

6. 디버깅-HTML-CSS(크롬 개발자도구의 Element Panel)
    - 크롬 웹페이지 내에서 우클릭 -> 요소 검사(Inspect)
    - select 누르고 알고싶은 부분 마우스 올리면 해당 엘리먼트 정보 나옴
    - Elements: 엘리먼트들 구조 코드 정보
    - Styles: 해당 스타일 정보
    - Computed: 최종 계산된 정보

---
### (4) 개발환경 설정 - BE
1. JDK 설치
    - JRE(Java SE Runtime Environment): JAVA 작성 프로그램 실행시 필요
    - JDK(Java SE Development Kit): 개발자 도구 (JRE 포함)
    - [window OS용 설치 링크](http://www.oracle.com/technetwork/java/index.html)
    - [mac OS용 설치 링크](http://www.oracle.com/technetwork/java/javase/downloads/index.htm)

2. 환경설정
    - 설정해야할 변수 3가지(시스템환경변수2 + 기존환경변수1)
      - JAVA_HOME: JAVA가 설치된 경로 지정
      - CLASSPATH: JAVA 클래스 있는 경로 지정
      - PATH: JAVA 실행파일이 있는 경로 추가
    - `vi /etc/paths`에 아래 경로 입력
      ```
        /Library/Java/JavaVirtualMachines/[해당jdk버전].jdk/Contents/Home/bin
      ```
    - `vi /etc/profile`에 아래 내용 입력
      ```
        export JAVA_HOME=/Library/Java/JavaVirtualMachines/[해당jdk버전].jdk/Contents/Home
        export CLASSPATH=.:$JAVA_HOME/lib/tools.jar

      ```

3. 이클립스 설치 및 인코딩 설정
    - 이클립스란?
      - 통합개발환경 (Integrated Development Environment, IDE)
      - 코딩, 디버그, 컴파일, 배포 등 프로그램 개발 관련 모든 작업을 한 프로그램 안에서 처리
      - 플러그인 구조: 쉽게 기능 추가
      - `Eclipse IDE for Java EE Developers` 설치
      - `/Users/oliver/eclipse/jee-oxygen` 경로에 위치
    - 인코딩 설정(맥 OS)
      - Eclipse -> Preferences -> General -> Workspace에서 UTF-8 설정
      - Preferences -> Web -> HTML, CSS, JSP Files -> UTF-8로 설정

4. HelloWorld 컴파일 및 실행
    - Java Code Conventions
      - Class 명: 첫글자 대문자
      - Project 명, Package 명: 소문자

5. Tomcat 설치
    - Apache Tomcat이란?
      - WAS(Web Application Server)
      - 자바 이용하여 작성된 웹 어플리케이션은 WAS 필요
      - 가장 많이 사용하는 WAS가 톰캣
    - [톰캣 설치하기](http://tomcat.apache.org/)(맥 OS)
      - Tomcat 9 -> Core -> tar.gz 설치
    - 압축 해제 후 폴더로 이동
    - 폴더 내에서 `./bin/startup.sh`로 실행
    - `http://localhost:8080/` 로 웹 사이트 확인
    - `./bin/shutdown.sh`로 종료

6. HelloWorld 서블릿 컴파일 및 실행
    - 자바 웹 어플리케이션 만들기
      - New -> Dynamic Web Project
      - Target Runtime -> Apache Tomcat 9.0 설정
    - HelloWorld 서블릿 컴파일
      - 서블릿: URL 요청을 처리하는 프로그램
      - New -> Servlet
      - Java Package: examples
      - Class name: HelloServlet
      - URL 주소 형식: `http://localhost:8080/{프로젝트이름}/{URL Mapping값}`
        - 여기서는 `http://localhost:8080/firstweb/HelloServlet`
      - doGet만 남기고 체크 해제


---
## 참조
  * [부스트 코스 강의](http://www.edwith.org/boostcourse-web)
