---
layout: post
title: "[요약] 후니의 쉽게 쓴 시스코 네트워킹 - 1"
description: "후니의 쉽게 쓴 시스코 네트워킹 책을 읽으며 요약한 포스팅입니다."
tags: [network]
published: true
comments: true
image:
  feature: network.jpg
---

---
## <span style="color:blue"> *Part 01 네트워크 세상에 들어서며* </span>
### 1. Networking: 장비들을 서로 대화가 가능하도록 묶어주는 것

### 2. Internet: 여러 개의 네트워크를 묶는 네트워크 연합
  - 인터넷 주소 시작인 www(world wide web): 세상을 거미줄처럼 묶겠다
  - TCP/IP라는 공통의 프로토콜 사용
  - 익스플로러 크롬 등의 웹 브라우저를 이용해 인터넷을 탐험
  - 필요한 정보는 무엇이든지 있다

### 3. IntraNet: 내부의 네트워크
  - TCP/IP 프로토콜 사용
  - 회사의 직원 사용(사내 네트워크)

### 4. ExtraNet
  - 회사의 직원 사용
  - 협력 회사나 고객도 사용

---

## <span style="color:blue"> *Part 02 네트워크와 케이블 그리고 친구들* </span>
### 1. LAN(Local Area Network): 한정된 공간에서 네트워크 구성
  - 사무실에 LAN을 구축하는 것
  - PC방에 각 PC 네트워킹하는 것

### 2. WAN(Wide Area Network): 멀리 떨어진 지역 서로 연결
  - 인터넷은 WAN으로 봐야함
  - 요즘 네트워크라 하면 주로 LAN과 WAN이 공존함

### 3. Ethernet: 데이터 네트워킹의 방식 1(인터넷의 친척 정도)
  - 속도: 100/1000Mbps
  - CSMA/CD라는 프로토콜 사용
  - 주로 회사나 학교에서 사용
  - 우리나라는 거의 대부분이 이더넷 방식 사용
  - 전세계에 수천 개 <-> (Internet은 1개)
  - 제한적, 상대적 안정적 <-> (Internet은 보안 위험 노출, 예방 조치 필요)

### 3-1. CSMA/CD(Carrier Sense Multiple Access/Collision Detection)
  1. Carrier Sense: 이더넷 환경에서 통신 하고 싶은 PC나 서버는 네트워크 자원 쓰고 있는 PC나 서버가 있는지 확인
  2. Multiple Access: 두 PC나 서버가 동시에 네트워크에 데이터 실어 보냄
  3. Collision Detection: 이 때, 데이터를 동시에 보내려다 부딪치는 경우 충돌이 발생  => 따라서 데이터를 네트워크에 실어 보내고 나서도 콜리전 발생여부 점검해야 함

### 4. TokenRing: 데이터 네트워킹의 방식 2
  - 속도: 4Mbps/16Mbps
  - 토큰 가진 PC만이 네트워크에 데이터 실어 보냄
  - 데이터 다 보내고 옆 PC에게 토큰 건내 줌
  - 장점: 충돌(Collision) 발생하지 않음
  - 단점: 내 차례 올 때 까지 기다려야 함 <-> (이더넷은 순서없이 아무나 통신)
  - IBM에 의해 처음 개발

### 5. 통신 케이블
  1. UTP(Unshielded Twisted Pair) 케이블
    - 카테고리 1: 주로 전화망에 사용, 데이터 전송용 X
    - 카테고리 2: 데이터 최대 4Mbps속도 전송
    - 카테고리 3: 10 Base T 네트워크에 사용, 최대 10Mbps 속도
    - 카테고리 4: 토큰링 네트워크에 사용
    - 카테고리 5: Fast Ethernet용, 기가비트 속도 가능(8가닥 모두 사용해야 가능)
  2. STP(Shielded Twisted Pair) 케이블: 절연체
    - 토큰링 쪽에 쓰임
    - 더 비싸고 성능이 좋음
    - EMI를 줄임
  3. 우리가 많이 쓰는 케이블
    - 10 Base 5: 10Mbps로 통신, 500미터 전송 가능
    - 10 Base FL: 10Mbps 통신, 광케이블(fiber-optic), ST 커넥터 사용
    - 100 Base TX: Category 5 UTP 케이블, 100Mbps 통신, 최대 거리 100미터

### 6. Mac(Media Access Control) Address: 랜카드 또는 네트워크 장비에 고정되어 있는 유일한 주소
  - 인터넷: TCP/IP통신 + IP주소 사용
  - ARP(Address Resolution Protocol): IP주소 -> MAC주소 바꾸는 절차
  - Physical Address(하드웨어 주소) <-> Logical Address(IP 주소)
  - 48bit(6octet)
  - LAN상의 device는 반드시 유일한 맥 어드레스 가짐
  - Ex) 00:60:97:8F:4F:86
  - 앞 6자리: 벤더, 생산자, OUI(Organizational Unique Identifier) 코드
  - 뒤 6자리: 각 장비에 분배, Host Identifier, Serial Number

### 7. 네트워크에서 통신 하는 방식에 따른 구분
  * Unicast: 1대1로 하는 방식
    - 가장 많이 사용되는 트래픽, 통신 방식
    - 출발지와 목적지 주소, 맥 어드레스 있어야 함
    - 어떤 PC가 유니캐스트 프레임 뿌리면 => 로컬 네트워크 상 PC는 프레임을 받아, 랜카드에서 자신의 맥 어드레스와 비교 => 다르면 프레임 버림(그 PC의 CPU까지 영향 X) <-> 브로드캐스트(PC성능 저하)
  * Broadcast: 전부를 대상으로 통신하는 방식
    - 로컬 랜(브로드캐스트 도메인)상의 모든 네트워크 장비들에게 보내는 통신
    - 방송을 하면 들리는 영역
    - 브로드캐스트의 주소(맥 어드레스 주소)가 오면 -> 랜카드는 자신의 맥 어드레스와 같이 않지만, 브로드캐스트 패킷을 CPU에 보냄(인터럽트) -> CPU가 처리(성능 저하)
    - 처음 두 PC간에 통신을 하는 경우(상대 IP주소는 알지만 맥 주소 모를 때) 사용
    - Ex) ARP과정: "이 주소 가진 사람 누구야?"(브로드캐스트) -> "나야"(맥어드레스)
    - 라우터끼리 정보 교환, 다른 라우터 찾을 때 사용
    - 서버들이 서비스 제공을 모든 클라이언트에게 알릴 때 사용
    - 30초나 1분에 주기적으로 발생
    - 필요하긴 하지만 많으면 문제가 됨
  * Multicast: 그룹을 대상으로 통신하는 방식
    - 그룹 멤버들에게만 한 번에 보냄
    - 라우터나 스위치에 기능 지원 있어야 함

### 8. OSI(Open Systems Interconnection) 7 Layer (에-프-스-트-엔-들-피)
  - L7, Application Layer
  - L6, Presentation Layer
  - L5, Session Layer
  - L4, Transport Layer
  - L3, Network Layer(Ip주소 헤더): 라우팅(데이터 목적지까지 안전, 빠르게 전달) ex) 라우터
  - L2, Data Link Layer: 맥어드레스로 통신 ex) 브리지, 스위치
  - L1, Physical Layer: 1과 0으로 데이터 전달 ex) 통신 케이블, 리피터, 허브
  - 장점: 문제 해결 쉬움, 여러 회사 장비 사용 가능
  - 내가 보낸 메일 각 단계 내려가면서 포장+헤더붙음 => 친구 PC 받으면 포장 하나씩 벗김

### 9. Protocol: 컴퓨터끼리 통신하기 위해 필요한 통신 규약
  - 프로토콜 같은 것 끼리만 통신 가능
  - 인터넷: TCP/IP(Transmission Control Protocol/Internet Protocol) 프로토콜
  - PC방 내부: IPX(Internetwork Packet Exchange)
  - 매킨토시: AppleTalk

---
## 참조
  * [후니의 쉽게 쓴 시스코 네트워킹](http://www.kyobobook.co.kr/search/SearchCommonMain.jsp)
