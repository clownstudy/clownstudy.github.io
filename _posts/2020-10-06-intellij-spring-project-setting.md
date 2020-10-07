---
title: "Intellij를 활용한 Spring Project 세팅"

categories:
    - Java
tags:
    - Java
    - Intellij
    - Spring
    - maven
toc: true
toc_label: "목차"
toc_sticky: true
last_modified_at: 2020-10-07
---

참고 사이트 : [[IntelliJ] Spring MVC, Maven 프로젝트 설정 방법](https://whitepaek.tistory.com/41){: target="_blank"}

## 개발 환경

- OS : Windows10
- IDE : Intellij 2020.2.3 (Ultimate Edition)
- Framework : Spring + Maven
- DB : Oracle

### 1. Maven 프로젝트 생성

<figure style="width:80%" class="align-center">
	<img src="/assets/img/intellij-spring-setup1.png">
	<figcaption> 1.1 Intellij 메뉴 </figcaption>
</figure>

File > New > Project를 선택
.
<figure style="width:80%" class="align-center">
	<img src="/assets/img/intellij-spring-setup2.png">
	<figcaption> 1.2 project 선택 창 </figcaption>
</figure>

Maven을 선택 후 Project SDK에서 본인이 사용할 Java 버전 선택 후 Next.

<figure style="width:80%" class="align-center">
	<img src="/assets/img/intellij-spring-setup3.png">
	<figcaption> 1.3 프로젝트 Name 설정 </figcaption>
</figure>
groupId는 프로젝트를 고유하게 식별해주는 식별자 역할을 한다.<br>
따라서 groupId는 네이밍 스키마<sup>[[1] 네이밍스키마?](#footnote_1)</sup>를 적용하도록 한다.<sup>[[2]출처](#footnote_2)</sup>

artifactId는 버전 정보를 생략한 jar파일의 이름이다.<sup>[[3]출처](#footnote_3)</sup><br>
이름은 아무거나 정해도 괜찮지만 소문자로만 작성하고 특수문자는 사용하지 않는다.<br>
일반적으로 프로젝트 명을 따라간다.


----
[[1] 네이밍스키마?](#footnote_1) : 명명규칙...이겠지?<br>
[[2],[3] 출처](#footnote_2) : [https://johngrib.github.io/wiki/groupId-artifactId/](https://johngrib.github.io/wiki/groupId-artifactId/){: target="_blank"} <br> 


