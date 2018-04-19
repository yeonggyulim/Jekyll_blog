---
layout: post
title: "[요약] 후니의 쉽게 쓴 시스코 네트워킹 - 6"
description: "후니의 쉽게 쓴 시스코 네트워킹 책을 읽으며 요약한 포스팅입니다."
tags: [network]
published: true
comments: true
image:
  feature: network.jpg
---
---

## <span style="color:blue"> *Part 11 선이 없는 세상, 무선으로의 여행* </span>
### 1. Access Point
  - 한쪽 발은 유선, 한쪽 발은 무선에 양다리 걸치고 서로 연결해주는 역할
  - AP가 있어야 무선통신 가능 => 무선통신 중이라면 주위에 AP 있을 것임
  - 유선네트워크라면 AP의 역할은 허브와 비슷(어느 한 순간에는 한 녀석과만 통신 가능)

### 2. 무선 랜
  - 무선 랜 통신 방식: CSMA/CA(Carrier Sense Multiple Access/Collision Avoidance)

### 3. 무선 랜의 두 가지 모드(개인 컴퓨터에 무선 랜 카드 세팅 프로그램에서 설정 가능)
  - Ad Hoc Mode(특별한 or 임시변통의 모드)
    - 무선 네트워킹에 꼭 필요한 AP 사용하지 않고, PC에 무선 랜 카드 꽂아 임시변통으로 통신 방식
    - PC들끼리 AP를 통하지 않고 무선으로 통신하는 방식
    - 임시변통이므로 권장 X, 소규모 통신만 가능(전달해야 할 파일 있을 때)
    - Service Set
      - Independent BSS
  - Infrastructure Mode
    - 일반적으로 사용하는 AP 사용 무선 통신 모드
    - 무선 랜 카드 장착 PC는 데이터를 AP에 전달 -> AP가 데이터 상대방 PC에 전달
    - 2 가지 모드의 서비스 방식(Service Set)
      - BSS(Basic Service Set)
        - AP 1대를 이용하여 무선 랜 구성하는 방식
        - 가정에서 구성되는 무선 랜
      - ESS(Extended Service Set)
        - AP 여러 대를 이용해 무선 랜 구성하는 방식
        - 넓은 지역 or AP 한 대로 무선 장비 접속 커버하기에 용량 부족할 때
        - 회사에서 구성되는 무선 랜
        - 주파수 간 간섭 발생 않는 비중첩 채널 사용해야함

### 4. 무선 통신에서 인코딩 3가지
  - FHSS(Frequency Hopping Spread Spectrum): 주파수 호핑 확산 스펙트럼 방식
    - 무선 신호를 주파수 채널로 빠르게 바꿔가면서(hopping) 전송하는 방식
    - 잡음과 간섭 같은 고질적인 통신 문제에 강점 있는 방식
  - DSSS(Direct Sequence Spread Spectrum): 직접 시퀀스 확산 스펙트럼
    - 여러 개의 채널 중 하나를 잡고 계속 그 채널로만 전송 하는 방식
    - 신호를 매우 작은 전력으로 넓은 대역으로 전송
    - 잡음에 영향 적게 받고, 낮은 전력 사용으로 다른 통신에 영향 덜 줌, 보안에 우수
    - 최대 11개(한국은 13개) 채널 지원, 이중 비중첩 채널은 3개
  - OFDM(Orthogonal Frequency Division Multiplexing): 직교 주파수 분할 다중 방식

### 5. SSID(Service Set Identifier)
  - 서비스 셋에서 서로 구분하기 위해 만들어 놓은 ID(32byte)
  - 무선 네트워크 안에 있는 무선 장비들은 모두 같은 SSID 가짐
  - 무선 네트워크의 이름들(와이파이 이름들)
  - 디폴트로는 무선 네트워크에서 100ms마다 SSID와 기타 구성 정보를 Broadcast로 네트워크에 뿌려줌
  - SSID Cloaking: SSID의 Broadcast를 Disable => SSID(와이파이) 아무나 못 봄
  - WIFI란? Wireless Fidelity
    - 좋은 무선 장비들의 호환성 검증(Hi-Fi: 좋은 오디오에 붙여줌)

### 6. 무선 네트워크에서의 보안
  - 통제 쉽지 않아 보안 중요함 <-> 회사내부 네트워크는 회사에 침입해 케이블 연결해야함
  - 2가지 보안 기법
    - Authentication(인증): 접속 허가 결정
    - Encryption(암호화): 데이터 자체를 암호화
  - WEP(Wired Equivalent Privacy): 맨 처음 무선 네트워크 사용된 보안 표준
    - 클라이언트 장비(노트북)와 액세스 포인트가 같은 Key값 나눠가짐
    - 접속 시도 시에 Key값이 같을 경우에 접속 허락 방식
    - key(40bit)는 Static이므로 바꿔주지 않으면 보안 취약
    - 해커가 네트워크 트래픽 캡처 후에 WEP키를 찾아내어 들어올 수 있음, 보안 취약
  - Cisco
    - 802.1X 사용자 인증 방식 통해 보안 강화
    - username과 password 이용한 방식
  - WPA(Wi-Fi Protected Access) (표준은 아니지만 많이 씀)
    - WEP의 보안 약점 해결한 새로운 무선 랜 보안 방식
    - Dynamic 키 방식 추가(키 값이 자동으로 바뀜)
    - TKIP(Temporal Key Integrity Protocol): 강화된 Encryption(암호화) 기법
  - WPA2: 802.11i (표준)
    - WPA에 TKIP => AES(Advanced Encryption Standard Encryption) 방식 사용


---
## 참조
  * [후니의 쉽게 쓴 시스코 네트워킹](http://www.kyobobook.co.kr/search/SearchCommonMain.jsp)
