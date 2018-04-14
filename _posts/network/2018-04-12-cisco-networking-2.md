---
layout: post
title: "[요약] 후니의 쉽게 쓴 시스코 네트워킹 - 2"
description: "후니의 쉽게 쓴 시스코 네트워킹 책을 읽으며 요약한 포스팅입니다."
tags: [network]
published: true
comments: true
image:
  feature: network.jpg
---
---

## <span style="color:blue"> *Part 03 TCP/IP와의 만남* </span>
### 1. TCP/IP(Transmission Control Protocol/Internet Protocol)
  - 인터넷을 쓰기 위한 필수 조건
  - 인터넷의 공용어
  - 인터넷 사용하는 모든 PC는 TCP/IP 세팅 되어있음
  - ARPANET에 의해 처음 개발
  - InternNIC(Internet Network Information)에서 호스트 고유 주소 관리 분배

### 2. IP 주소
  - 전 세계에서 유일하게 나만이 가지고 있는 것
  - 인터넷 사용유저는 모두 서로 다른 IP주소 가짐
  - NAT(Network Address Translation): 내부 네트워크에선 공인X IP사용 => 인터넷 나갈 때만 고유 IP주소 사용
  - PAT(Port Address Translation): 동일한 IP주소로 포트 넘버만 바꿔 여러 명이 인터넷에 접속 ex) 공유기
  - 인터넷을 제대로 사용하기 위해서는 고유 IP주소가 있어야 한다.
  - NIC(Network Information Center)가 공인 주소 나눠주고 관리
  - Ex) 192.168.1.100
  - 만들 수 있는 주소의 개수: \\({2}^{32}\\)


---

## <span style="color:blue"> *Part 04 네트워크 장비들에 관한 이야기* </span>
### 1. LAN card: NIC(Network Interface Card) 혹은 Network Adapter
  - Plug and Play: PC에 랜카드 꽂고 전원 껐다 켜면 PC가 알아서 랜카드 인식, 필요한 프로그램 설치, 네트워크 연결해주는 기능
  - 유저의 데이터를 케이블에 실어 허브나 스위치, 혹은 라우터 등으로 전달해주고 자신에게 온 데이터를 CPU에 전달하는 역할
  - 어떤 환경에 사용하는가에 따라 이더넷용 랜카드, 토큰링용, 그리고 FDDI, ATM용 등으로 구분
  - 대부분의 환경 90% 이상은 이더넷용 랜카드 사용
  - 데스크탑용 랜카드와 노트북용 랜카드(PCMCIA 방식)이 있음
  - 프린터 포트 연결하는 외장형 랜카드, USB포트에 연결하는 방식도 있음
  - 데스크탑용에는 PC 버스 방식을 보고 맞춰 사야 함
    1. PCI방식: 현잭 가장 많이 사용
    2. ISA(아이사)
    3. EISA(이아이사)

### 2. HUB (Shared Ethernet) (1차선 도로)
  - 스위치가 싸져서 요즘에는 잘 안씀
  - 그래도 랜카드, 케이블, 그리고 허브만 있으면 내부에 허브 접속 모든 PC들이 서로 통신이 가능해짐
  - Multiport Repeater: 포트 여러개 + 한 포트로 들어온 데이터 나머지 모든 포트로 뿌림
  - 리피터: 중간에 들어온 데이터를 다른 쪽으로 전달해 주는 역할(엠프처럼)
  - 리피터 -> 허브 -> 브리지 -> 스위치 -> 라우터로 흐름이 바뀐 듯
  - 허브 붙어 있는 모든 것: 같은 콜리전 도메인(이더넷 허브: CSMA/CD)
  - 장점: 저렴, 일반적으로 데이터 처리 스위치보다 빠름, 채팅이나 메일시에 사용
  - 한계: 안전성 + Shared 허브(모든 PC가 하나의 콜리전 도메인에 있어 한 PC만 데이터 보냄, 속도를 다 공유함)
  - HUB의 한계인 콜리전 도메인을 나누어 줄 수 있는 장비 => 브리지와 스위치
  - 종류
    1. Intelligent HUB: NMS를 통해 관리, 분석 및 제어 가능, 문제 포트 방출
    2. Dummy HUB
    3. SemiIntelligent HUB: 혼자 있을 땐 더미 허브, 인텔리랑 있으면 인텔리전트 허브 되는 허브
    4. Stackable HUB: 여러 대 스택으로 연결되면 훨씬 더 좋은 성능을 발휘
    5. Standalone HUB: 서로 연결이 안되는 건 아님, 효율이 좋진 않음

### 3. Switch (Switched Ethernet) (8포트 스위치: 8차선 도로)
  - 모든 기능은 브리지에서 출발
  - Switching Hub도 Switch임
  - 1번 포트와 2번포트 PC 데이터 교환 시에 3번 포트와 4번 포트 PC 데이터 교환 가능
  - 포트별로 콜리전 도메인이 나뉘어져 있다!
  - 10Mbps 또는 100Mbps가 독자적인 속도임
  - 속도가 빨라서 PC방에서도 스위치 많이 사용
  - 스위치 가격이 줄어들면서, 허브 잘 안쓰고 스위치 사용함

### 4. Bridge
  - 스위치의 원조격(브리지의 모든 특성 -> 스위치의 모든 특성)
  - 허브로 만들어진 콜리전 도메인 사이를 반으로 나누고 중간에 다리르 놓음
  - 남단끼리, 북단끼리 동시 통신 + 남->북 갈 때 브리지 이용

### 5. 브리지와 스위치의 기능 (같은 L2 장비)
  - Learning: 출발지의 맥 어드레스를 배운다
  - Flooding: 들어온 포트를 제외한 다른 모든 포트로 뿌린다.(브리지 테이블에 없는 주소일 때)
  - Forwarding: 해당 포트로 건네준다.(맥 어드레스가 브리지 테이블에 있고, 다른 세그먼트에 있을 때)
  - Filtering: 포트 막음, 콜리전 도메인 나눔(브리지 테이블에 있고, 같은 세그먼트에 있을 때)
  - Aging: 디폴트 5분 후에 브리지 테이블에 맥 어드레스 지움(Refresh: Aging Timer Recount)
  - 맥주소가 브리지 테이블에 없다면 X, 있다면 O
  - (1) X: Learning <-> O: Aging Timer Refresh
  - (2) X: Learning 후에 Flooding <-> O: Refresh 다음 Filtering or Forwarding

### 6. 브리지와 스위치의 차이점
  - 스위치는 하드웨어 처리 방식(빠르다) <=> 브리지는 소프트웨어 프레임 처리 방식
  - 스위치는 서로 다른 속도 연결 기능 제공 <=> 브리지는 포트별 같은 속도 지원
  - 스위치는 제공하는 포트 수 많음(몇십 몇백 개) <=> 브리지는 보통 2~3개 포트 가짐
  - 스위치는 cut-through 또는 store-and-forward <=> 브리지는 store-and-forward
  - Store-and-forward: 스위치나 브리지가 들어오는 프레임 전부 받아들인 다음 처리 시작 방식
  - Cut-through: 스위치가 들어오는 프레임의 목적지 주소 본 다음 전송 처리 시작 방식(48비트)
  - Fragment-Free: 2가지 장점 결합한 방식, 처음 512비트 보고 에러 감지함

### 7. Looping (브리지나 스위치에서 자주 발생)
  - 프레임 네트워크 루프시에 전송 불가능 상태(이더넷은 네트워크 조용해야 전송 가능)
  - 스위치나 브리지에 두 개 이상의 경로 만들어지면 루핑 발생
  - 두 개의 브리지가 목적지 주소 보고 Flooding 하는 것
  - Spanning Tree Algorithm 필요

### 8. Fault tolerant (장애 대비책, 이중 구조)와 Load balancing
  - Fault tolerant: 전체 네트워크가 하나의 장애 발생으로 인해 끊김 방지 대책
  - Load balancing: 인터넷 회선 2개 사용, 2라인 중 1 사용 => 로드 분산 효과(속도 2배)
  - 로드 밸런싱 => 폴트 톨러런트 O 가능, 폴트 톨러런트 => 로드 밸런싱 X 불가능

### 9. Spanning Tree Algorithm
  - 스위치 간의 2개 링크 중 1개 끊어 놓음 => 한 쪽으롬나 다니게 함
  - 하나의 링크가 끊어졌을 때 다른 링크가 다시 연결 해주는데 1분 이상 소요
  - 이 알고리즘 보안 방법: 시스코의 Ether-Channel 기술: 여러 개 링크가 하나 링크 처럼 인식

### 10. Router 필요한 이유
  - 브로드캐스트 영역(도메인)을 나누기 위함
  - 라우터는 패킷 필터링 기능 제공 <=> 스위치 못함
  - 로드 분배: 데이터 여러 경로로 보냄
  - QoS(Quality of Service) 기능 제공: 데이터 크기 중요도에 따라 트래픽 전송 순서 조정
  - 스위치와 라우터를 적당히 사용해야 함

---
## 참조
  * [후니의 쉽게 쓴 시스코 네트워킹](http://www.kyobobook.co.kr/search/SearchCommonMain.jsp)
