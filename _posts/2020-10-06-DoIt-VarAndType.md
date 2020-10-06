---
title: "진수, 음의 정수 표현"

categories:
    - Do it Java
tags:
    - Java
    - Inflearn
toc: true
toc_label: "목차"
toc_sticky: true
---
[인프런의 Do it! 자바 프로그래밍 입문 - 변수와 자료형(1)](https://www.inflearn.com/course/%EC%9E%90%EB%B0%94-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%9E%85%EB%AC%B8/lecture/18012){: target="_blank"}

### 10진수와 16진수

<pre>
10진수 9 10 11 12 13 14 15 16
16진수 9 A  B  C  D  E  F  10  
</pre>

### Java에서 진수별 표현 방법
<font size="3">각 진수별로 10을 표현해보자</font>
<font size="4">
<pre>
2진수 : 앞에 0B를 붙인다. ex) int num = 0B1010;
8진수 : 앞에 0을 붙인다. ex) int num = 012;
16진수 : 앞에 0x를 붙인다 ex) int num = 0xA;
</pre>
</font>

### 음의 정수 표현
<font size="3">일반적으로 정수는 32bit로 표현, 8자리

5를 음수로 표현해보자.</font>

<pre>
0 0 0 0 0 1 0 1
// 1. 더해서 모두 1이 나오는 수를 구한다.(1의 보수)
1 1 1 1 1 0 1 0
// 2. 여기에 +1을 한다.
1 1 1 1 1 0 1 1 
// 처음 수와 더하면 8자리는 0으로되고 맨 앞자리는 1이 되지만 비트 범위를 넘어가서 truncate 처리 됨.

// 이게 2의 보수를 취한 것.
즉, 2의 보수를 취하면 음의 정수로 표현됨.
</pre>