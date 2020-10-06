---
title: "항과 연산자"

categories:
    - Do it Java
tags:
    - Java
    - Inflearn
toc: true
toc_label: "목차"
toc_sticky: true
---
[인프런의 Do it! 자바 프로그래밍 입문 - 자바의 여러가지 연산자(1)](https://www.inflearn.com/course/%EC%9E%90%EB%B0%94-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%9E%85%EB%AC%B8/lecture/18015){: target="_blank"}

## 항과 연산자

* 항(operand): 연산에 사용되는 값
* 연산자(operator): 항을 이용하여 연산하는 기호

### 항의 개수에 따른 연산자 구분

|연산자|설명||연산 예|
|:------:|:----:||:------:|
|단항 연산자|항이 1개||++num||
|이항 연산자|항이 2개||num1 + num2;|
|삼항 연산자|항이 3개||(5>3)?1:0;|

### 증감 연산자
* 단항 연산자
* 1만큼 더하거나 뺄 때 사용
* 항의 앞/뒤 위치에 따라 연산의 결과가 달라짐

|연산자|기능||연산 예|
|:-----:|:----:||:-------:|
|++|항의 값에 1 더함||val = ++num; // num에 1을 먼저 더한 후 val에 대입 <br> val = num++; // val에 기존 num값 대입 후 num값 1 증가 <br>|
|- -|항의 값에서 1 뺌||val = - -num; // num에 1을 먼저 뺀 후 val에 대입 <br> val = num- -; // val에 기존 num값 대입 후 num값 1 감소|