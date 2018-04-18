---
layout: post
title: "[요약] 후니의 쉽게 쓴 시스코 네트워킹 - 5"
description: "후니의 쉽게 쓴 시스코 네트워킹 책을 읽으며 요약한 포스팅입니다."
tags: [network]
published: true
comments: true
image:
  feature: network.jpg
---
---

## <span style="color:blue"> *Part 07 라우터만 알면 네트워크 도사?* </span>
### 1. Router란? 지능을 가진 경로 배정기
  - 우리에게 필요한 것: 네트워크에 대한 개념
    - 네트워크 IP에 대한 이해, 서브넷 마스크에 대한 이해, 라우팅에 대한 이해
    - IPX, EDCNET, AppleTalk등 많은 프로토콜 라우팅 있지만 우리는 IP 라우팅 공부!
    - 시스코 라우터가 전 세계 인터넷의 80% 이상 차지 이것을 공부!
  - 2가지 일 수행 (이를 위해 라우팅 테이블 만들어 관리하는 라우팅 알고리즘 사용)
    - Path Determination(경로 결정): 데이터 패킷의 목적지까지 길 검사 + 적절한 길 결정
    - Switching(스위칭): 길 결정 후에 그쪽으로 데이터 패킷을 스위칭해 줌
  - 라우터는 PC처럼 CPU, 메모리, 인터페이스 가지고 있음
  - 인터페이스: 라우터의 접속 포트
    - Ethernet 포트: 내부 네트워크(LAN)을 위한 접속 포트
    - Serial 포트: 외부 네트워크(WAN)을 위한 접속 포트 DSU/CSU와 연결
  - Routed Protocol
    - 라우터가 라우팅 해주는 프로토콜(라우터라는 자동차 타는 승객)
    - ex) TCP/IP, IPX, AppleTalk 등 우리가 아는 모든 프로토콜
  - Routing Protocol(라우팅 알고리즘이라고도 함)
    - 라우티드 프로토콜 목적지까지 가게 해줌(자동차 안전하고 빠르게 운전하는 운전기사)
    - ex) RIP(Routing Information Protocol), IGRP, OSPF, EIGRP 등
    - 라우팅 테이블(메모리) 가짐 (찾아갈 경로에 대한 정보 저장: 목적지, 거리, 어떻게 갈지)
    - Static Routing Protocol: 라우터에 사람이 일일이 경로 입력(빠르고 좋은 길)
      - 속도 빠름, 성능 좋음, 메모리 적게 듬
      - 라우팅 테이블 교환할 필요 X => 네트워크 대역폭 절약 가능
      - 보안에 강함
      - 단점: 귀찮음, 문제 생기면 커짐
      - 주로 작은 규모 네트워크 연결 시에 사용
    - Dynamic Routing Protocol
      - 경로 입력 필요 X, 알아서 좋은 길 찾음
      - 단점: 라우터에 부담, 할 일 많음
      - 네트워크 센터같이 많은 경로 처리하는 경우 사용
    - Routing Table(네트워크에 대한 지도)
      - IP주소 보고 맞는 포트로 보냄
      - 시스코 라우터: 테이블 보는 명령: show ip route
    - AS(Autonomous System): 하나의네트워크 관리자에 의해 관리되는 라우터들의 집단
    - interior Routing Protocol(내부 프로토콜)
      - ex) RIP, IGRP, EIGRP, OSPF
    - Exterior Routing Protocol
      - ex) EGP, BGP
  - 라우터 연결하는 방법 5가지!
    - Console Cable을 통한 구성
      - 콘솔 연결: 라우터 뒷면의 콘솔 포트 연결 + 컴퓨터 시리얼(직렬 or COM) 포트에 연결
    - 원격지 모뎀을 이용한 구성
    - IP주소 세팅 후 네트워크 통해 접속하는 텔넷 이용한 구성
    - NMS를 이용한 구성
    - 미리 구성 파일 저장했다가 나중에 라우터로 다운하는 TFTP 서버를 이용한 구성

  - 라우터의 중요한 몇 가지 모드(어떤 방식으로 구성하든)
    - User mode: '>'가 있는 모드
      - 테스트, 현재 상태 볼 수 있음
      - 핑, 트레이스 등 가능(라우터 구성 파일 혹은 구성 자체 변경 X)
      - enable: User -> Privileged
      - exit: 종료
    - Privileged Mode: 운영자 모드(enable 명령어), '#'이 있는 모드
      - 모든 라우터의 명령 가능
      - 구성 보거나 변경 가능
      - config terminal: Privileged -> Configuration
      - disable: Privileged -> User
    - Configuration Mode(구성 모드): 모든 구성 파일 여기서 만듬
      - 구성 파일 변경하는 경우 사용
      - 라우터 만지는 엔지니어들 필요
      - exit or Ctrl+Z: Configuration -> Privileged
    - Setup Mode: 처음 구매 후 파워 킬 때 라우터 구성파일 없는 경우
    - RXBOOT mode = ROMMON mode(복구용 모드)
      - 평소에 사용 X, 패스워드 모를 때, 이미지파일 문제 생길 때 복구 위해 사용
  - 라우터 내부 구조
    - RAM
    - 콘솔 포트
    - AUX 포트
    - 인터페이스
      - 네트워크와 라우터에 직접 연결되는 부분
      - 허브와 스위치: Ethernet Interface, DSU나 CSU: Serial Interface

---
## 참조
  * [후니의 쉽게 쓴 시스코 네트워킹](http://www.kyobobook.co.kr/search/SearchCommonMain.jsp)
