---
title:  "C++_Class_std"
excerpt: "C++에서의 클래스(Class) 공부기록"

categories:
  - Blog
tags:
  - C++
  - Class
---

#C++ 클래스 공부 기록.

  - 클래스와 구조체의 유일한 차이점.
    *단지 키워드를 struct가 아닌 class를 사용하는 것
      - 선언
        *Car run99={"run99",100,0}  (X)
        *Car run99; (O)
      - 초기화
        *클래스 내에 선언된 변수는 기본적으로 클래스 내에 선언된 함수에서만 접근이 가능하다.
  * 접근제어 지시자(접근제어 레이블)
    - public: 어디서든 접근허용
    - protected: 상속관계에 놓여있을 때, 유도 클래스에서의 접근허용
    - private: 클래스 내(클래스 내에 정의된 함수)에서만 접근허용_(상속과 관련)
    


