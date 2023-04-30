---
title: "JAVA GC"
excerpt: "자바 가비지 컬렉터의 동작 방식"

categories:
  - JAVA
tags:
  - [java, gc, garbage collectors]

permalink: /JAVA/java-garbage-collector/

toc: true
toc_sticky: true

date: 2023-04-30
last_modified_at: 2023-04-30
---

<h2> 설계 </h2>

자바의 가비지 컬렉터는 두가지 전제로 설계가 되었습니다. <br>
1. 객체는 보통 1회성으로 생성이 된다.
2. 오래살아남는 객체가 거의 없다.

<br>
<br>

<h2> 구성 </h2>

위에서 설명한 설계를 기준으로 크게 2가지 영역으로 나뉘었습니다. <br>
![java_gc_structure](/assets/images/posts_img/java-garbage-collector/java_gc_structure.png)
<br>

<h3> 1. Young 영역 </h3>
young 영역은 크게 3가지의 영역으로 1개의 Eden 영역과 2개의 Survive 영역으로 나뉩니다. <br>
<br>
Eden 영역은 객체가 생성되는 곳입니다. <br>
Eden 영역이 모두 꽉 찼을 경우 Minor GC 가 일어나는데 여기서 살아남은 객체들은 사용하고 있는 Survive 영역으로 이동하게 됩니다. <br>
<br>
Survive 은 한번 이상 살아남은 객체가 존재하는 곳입니다. <br>
Survive 영역은 두 개의 영역이 있지만 하나의 영역만 사용한다는 특징이 있습니다. <br>
사용하고 있는 Survive 영역이 모두 꽉 찼을 경우 GC 가 일어나게 되고 살아남은 객체들은 다른 Survive 영역으로 이동하게 됩니다.<br>
<br>

<h3> 2. Old 영역 </h3>
Old 영역은 Young 영역보다 크다는 특징이 있고, Survive 영역에서 일정 횟수(age) 만큼 살아남은 객체들이 Promotion 되어 복사되어 오는 영역입니다. <br>
Old 영역은 모두 꽉차게 되면 Major GC 가 일어나게 되는데 Young 영역보다 크기 때문에 10배 정도 오래걸린다는 특징이 있습니다. <br>
<br>
<br>

<h2> 동작 방식 </h2>
동작 방식은 크게 두가지로 나뉩니다.<br>
<br>
<h3> Stop the World </h3>
가비지 컬렉터를 실행하는 쓰레드를 제외하고 모든 쓰레드를 stop 시키는 단계입니다.<br>
<br>
<h3> Mark and Sweep </h3>
스택영역에 있는 변수들을 주소값으로 연결시켜 힙영역에 Mark 하고 Mark 되어 있지 않은 객체들을 메모리에서 제거하는 단계입니다.<br>
<br>
위 방식을 통해서 사용하지 않는 객체들을 메모리에서 제거하게 됩니다.


