---
layout: post
title: "Data Structure"
description: "생활코딩 자료구조 강의를 보며 보요약한 내용입니다."
tags: [data structure]
published: false
comments: true
image:
  feature: data-structure.jpg
---

---
### 1. 데이터 스트럭쳐란?
  - 현실을 프로그래밍적으로 표현하는 것
  - 큰 데이터를 효과적으로 관리하는 것
  - 데이터를 효율적으로 저장하고 꺼내기 쉽게 만드는 것
  - 메모리를 효율적으로 사용하는 것
  - RAM(Random Access Memory): 각각의 주소에 접근할 때 걸리는 시간 동일
  - 배열: 대표적인 데이터 스트럭쳐

### 2. 배열
  - 거의 모든 언어에서 지원하는 데이터 타입
  - 많은 자료구조에서 데이터 저장하기 위한 부품으로 사용
  - 여러 데이터를 하나의 이름으로 그루핑하여 관하기 위한 자료구조
  - 주로 반복문을 이용하여 배열 사용
  <img src="/images/data-structure/array.gif" alt="" />
  - 단점
    - 크기가 정해져 있음
    - 기능이 없음(삭제, 추가, 이동 등)
  - 장점
    - 작고 가볍고 단순함(크기 정해져 있고, 기능이 없음)

### 3. 리스트
  - 개념: 순서가 있는 엘리먼트의 모임
  - 빈 엘리먼트 허용 X
  - 중복 데이터 허용 O
  - 기능
    - 처음, 끝, 중간에 엘리먼트 추가/삭제하는 기능
    - 리스트에 데이터가 있는지 체크하는 기능
    - 리스트의 모든 데이터에 접근하는 기능
  - 위와 같은 기능 가지고, 순서가 있으며, 중복이 허된다면 리스트 자료구조라 부름
  - 자바스크립트는 배열이 리스트, 파이썬에서는 리스트만 지원(리스트가 배열)
  - 최근의 언어는 리스트를 기본적으로 지원
    - 자바스크립트: 배열이 리스트
    - 파이썬: 리스트만 지원(리스트가 배열)
    - 자바: 배열과 리스트 둘 다 각각 지원
  - 자바에서의 내장 리스트(2가지 구현 방법이 다름)
    - Java List API(사용법)
      - 생성
      ```java
        import java.util.ArrayList;
        ArrayList<Integer> numbers = new ArrayList<>();
      ```
      - 추가
      ```java
        numbers.add(10);
        numbers.add(1, 50);
      ```
      - 삭제
      ```java
        numbers.remove(2);
      ```
      - 가져오기
      ```java
        numbers.get(2);
      ```
      - 반복
      ```java
        Iterator it<Integer> = numbers.iterator();
        while(it.hasNext()){
            System.out.println(it.next());          
        }
      ```
      혹은
      ```java
        for (int value : numbers) {
          System.out.println(value);
        }
      ```

    - ArrayList:
      - List 만들 때 내부적으로 Array를 사용하여 리스트 구현
      - 인덱스 이용해 데이터 가져온다면 이게 더 빠름
    - LinkedList:
      - List 만들 때 엘리먼트 간 연결(link)를 이용해 리스트 구현
      - 추가/삭제가 빈번할 때 더 효과적
      <img src="/images/data-structure/linkedlist.png" alt="" />


---
## 참조
  * [생활코딩_자료구조](https://opentutorials.org/module/1335)
