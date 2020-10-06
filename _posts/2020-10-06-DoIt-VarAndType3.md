---
title: "상수와 형변환"

categories:
    - Do it Java
tags:
    - Java
    - Inflearn
toc: true
toc_label: "목차"
toc_sticky: true
---
[인프런의 Do it! 자바 프로그래밍 입문 - 변수와 자료형(3)](https://www.inflearn.com/course/%EC%9E%90%EB%B0%94-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%9E%85%EB%AC%B8/lecture/18014){: target="_blank"}

## 상수(constant)

* 상수 : 변하지 않는 값(변수와 반대되는 개념)
* 상수 선언 : final 키워드 사용

## 리터럴(literal)

* 리터럴 : 프로그램에서 사용하는 모든 숫자, 값, 논리값
* 리터럴에 해당되는 값은 특정 메모리 공간인 상수풀<sup>[1](#footnote_1)</sup> (constant pool)에 있음
* 필요 시 상수 풀에서 가져와서 사용
* 상수 풀에 저장 시 정수는 int, 실수는 double로 저장
* long이나 float로 저장 시 식별자(L,I,F,f)를 명시해야함.

## 형 변환 (type conversion/casting)

* 묵시적 형 변환 : 작은 수 -> 큰수 / 정수 -> 실수
* 명시적 형 변환 : 묵시적 형 변환과 반대의 경우 사용. 

-----
[[1]](#footnote_1):<https://bbchu.tistory.com/13>