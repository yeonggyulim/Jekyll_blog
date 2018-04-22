---
layout: post
title: "[요약] 후니의 쉽게 쓴 시스코 네트워킹 - 7"
description: "후니의 쉽게 쓴 시스코 네트워킹 책을 읽으며 요약한 포스팅입니다."
tags: [network]
published: true
comments: true
image:
  feature: network.jpg
---
---

## <span style="color:blue"> *Part 12 IPv6로 떠나는 여행* </span>
### 1. IPv4의 문제점
  - IPv4 주소의 공간 부족 => aggregation(라우팅 정보 하나로 묶어 테이블 줄임)이 어려움
  - IPv4의 복잡한 Header: 전체 필드 불필요하게 늘어남
  - IPv4의 IP 주소 배정 방식이 복잡 => DHCP로 해결, but 또 다른 서버의 구성(오버헤드)
  - 번거롭고 효율적이지 못했던 보안기능과 Mobile IP의 지원

### 2. IPv4의 문제 해결법
  - NAT(Network Address Translation)
    - 내부망에서는 Private IP주소, 내 맘대로 주소 쓰고, 인터넷으로 나갈 때만 공인 IP 주소 사용헫
    - 요즘 많이 사용하는 인터넷 공유기 역시 이런 원리 이용
    - IP 주소 변환해주는 시간 필요
    - End-to-End 기능 지원 프로그램 => 호환성에 문제 ex) NAT으로 인터넷 전화 잘 안되는 것
  - 서브넷팅: 네트워크 잘게 쪼개 씀
  - DHCP(Dynamic Host Configuration Protocol)가 안쓰는 주소 회수함: 주소 낭비 막음
  - CIDR(Classless Inter Domain Routing): 기존 클래스 약속 무시, 서브넷 마스크로 클래스 지정
    - 수퍼넷팅: 여러 개의 작은 네트워크를 한 개로 모아 라우팅 테이블 줄임 => 라우터 메모리 절약, 속도 업
  - 새로운 IP방식: IP version 6

### 3. IPv6 특징
  - 넓어진 주소 공간 => Global Address: 전 세계적으로 유일한 주소
    - flexibility: 융통성 + 주소를 체계적 배정
    - Prefix Aggregation 효과적 (주소 집합해서 하나의 주소 만드는 것)
    - multihoming: 한 곳에 문제 생겼을 때 돌아갈 곳 정해두는 방식
    - End-to-End Reachability: 한쪽 끝에서 다른 쪽 끝까지 주소 변환 없이 접속
  - IP header 구조 대폭 개선
    - 헤더 간소화, 효과적 배치 => 라우팅 성능 획기적으로 올림
  - 다양한 IPv4와의 호환옵션
  - 주소의 계층화(Hierarchical Addressing)
  - Auto Configuration
    - Stateless Auto Configuration: 특정 서버 없이 라우터에서 자동으로 호스트 IP구성 가능
    - 호스트(PC)의 IP 주소 걱정해 줄 필요 X
    - Plug and Play: 네트워크에 붙이면 자동으로 주소 만들어줌
  - Broadcast 대신 Multicast 사용
    - 4bit의 Scope ID 사용
  - Mobility


---
## 참조
  * [후니의 쉽게 쓴 시스코 네트워킹](http://www.kyobobook.co.kr/search/SearchCommonMain.jsp)
