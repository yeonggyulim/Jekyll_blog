---
layout: post
title: "[요약] 후니의 쉽게 쓴 시스코 네트워킹 - 4"
description: "후니의 쉽게 쓴 시스코 네트워킹 책을 읽으며 요약한 포스팅입니다."
tags: [network]
published: true
comments: true
image:
  feature: network.jpg
---
---

## <span style="color:blue"> *Part 06 스위치를 켜라* </span>
### 1. Spanning Tree Protocol Algorithm(STP)
  - 스위치나 브리지에서 발생하는 루핑을 막기 위한 프로토콜
  - 출발지->목적지 경로 2개 이상 일때 1개 빼고 끊어 두었다가 필요할 때 사용
  - 2가지 개념
    - Bridge ID: 브리지나 스위치가 통신할 때 서로 확인하기 위해 가지는 번호
      - Bridge Priority(16비트) + Mac Address(48비트)
    - Path Cost: 길을 가는데 드는 비용
      - 1000Mbps(고정값)/10Mbps(링크의 속도: 대역폭) = 100
  - 기본적인 3가지 동작
    - 네트워크당 하나의 Root Bridge를 선정한다.
    - Not Root Bridge당 하나의 Root Port를 선정한다.
    - Segment당 하나씩의 Designated Port(지정 포트)를 선정한다.
    - Root Port와 Designated Port아닌 나머지 모든 포트는 막아버린다.
  - STP에서 순서 정하는 단계
    - 누가 더 작은 Root BID를 가졌는가?
    - 루트 브리지까지의 Path Cost 값은 누가 더 작은가?
    - 누구의 BID(Sender BID)가 더 낮은가?
    - 누구의 포트 ID가 더 낮은가?
  - Bridge가 STP 정보를 자기들끼리 주고 받기 위해 특수한 프레임 사용
    - BPDU(Bridge Protocol Data Unit)
      - Root BID: 루트 브리지의 BID
      - Root Path Cost: 루트 브리지까지 가는 경로값
      - Sender BID: 보내는 브리지의 BID
      - Port ID: 어떤 포트에서 보냈는지 알게 해줌
    - 브리지나 스위치 부팅시에 각각 포트로 BPDU를 매 2초마다 내보내면서 STP 정보 주고 받음
    - 누가 루트 포트, 데지그네이티드 포트가 될지 결정함
  - Spanning Tree Protocol 5가지 변화
    - Disabled: 포트 고장 or 네트워크 관리자가 포트 Shut Down
      - 데이터 전송: X
      - 맥 어드레스 배움: X
      - BPDU 주고 받음: X
    - Blocking: 스위치를 맨 처음 켜거나 Disabled 포트를 관리자가 다시 살렸을 때
      - 데이터 전송: X
      - 맥 어드레스 배움: X
      - BPDU 주고 받음: O
    - Listening: Switch Port => Root Port or Designated Port 선정되면 리스닝 상태
      - 데이터 전송: X
      - 맥 어드레스 배움: X
      - BPDU 주고 받음: O
    - Learning: Listening => Forwarding Delay Default 15초 버티면 러닝 상태
      - 데이터 전송: X
      - 맥 어드레스 배움: O
      - BPDU 주고 받음: O
    - Forwarding: 스위치 포트가 러닝 상태에서 다시 포워딩 딜레이 디폴트 15초 버틴 상태
      - 데이터 전송: O
      - 맥 어드레스 배움: O(브리지 테이블 만듦)
      - BPDU 주고 받음: O

### 2. Virtual Lan(가상의 랜)
  - 스위치가 콜리전 도메인 나눠줌 + 가상랜 기능
  - 스위치만 지원 O <-> 허브, 브리지, 라우터는 지원 X
  - 한 대의 스위치를 여러 개의 네트워크로 나누기 위해 사용
  - 스위치가 VLAN으로 나누어지면(브로드캐스트 도메인) VLAN간의 통신은 라우터를 통해 가능
  - 스위치 안에 있는 스위치 각각을 VLAN이라 함
  - Trunk Port: 하나의 포트를 통해 여러 개 VLAN 전송하게 하는 포트
  - 트렁킹: 여러 개의 VLAN을 한 번에 전송하는 방식
  - VTP(VLAN Trunking Protocol): 스위치 간 VLAN 정보 주고받아 일치시키기 위한 프로토콜

---
## 참조
  * [후니의 쉽게 쓴 시스코 네트워킹](http://www.kyobobook.co.kr/search/SearchCommonMain.jsp)
