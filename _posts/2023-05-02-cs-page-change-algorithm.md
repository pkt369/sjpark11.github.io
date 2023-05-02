---
title: "메모리 교체 알고리즘"
excerpt: "메모리 교체 알고리즘이란"

categories:
  - CS
tags:
  - [CS, 메모리 교체 알고리즘, 페이징]

permalink: /CS/cs-page-replacement-algorithm/

toc: true
toc_sticky: true

date: 2023-05-02
last_modified_at: 2023-05-02
---

## 페이지 교체 알고리즘(page replacement algorithm)

필요한 페이지가 메모리에 없을 때 page-fault 가 발생하고 Backing Store 에서 해당 페이지를 찾아 빈 프레임에 로딩해야 하는데, 이때 빈프레임이 없을 경우 희생당할 프레임을 고르는 알고리즘이 페이지 교체 알고리즘입니다. <br>
<br>
페이지 교체 알고리즘은 page-fault 발생 비율을 줄이는 것이 목표입니다.<br>
<br>

## FIFO (First In First Out)
![FIFO](/assets/images/posts_img/cs-page-replacement-algorithm/FIFO.png) <br>
FIFO 알고리즘은 먼저 들어간것이 먼저 나오는 알고리즘입니다. <br>
흔히 알고 있는 Queue 와 동작방식이 같습니다. <br>
<br>
구현이 쉽지만 성능이 좋지않다는것이 특징입니다.<br>
<br>

## OPT (Optimal = 최적) 알고리즘 
![OPT](/assets/images/posts_img/cs-page-replacement-algorithm/OPT-Algorithm.png) <br>
OPT 알고리즘은 앞으로 일어날 페이지를 미리 알고 최적의 페이지 교체를 이루어내는 알고리즘입니다.<br>
최적의 알고리즘으로 page-fault 가 가장 작습니다.<br>
<br>

## LRU (Least Recently Used)
![LRU](/assets/images/posts_img/cs-page-replacement-algorithm/LRU.png) <br>
LRU 알고리즘은 가장 오래동안 사용되지 않은 페이지를 교체하는 알고리즘입니다.<br>
많은 운영체제가 채택한 알고리즘입니다.<br>
<br>

## LFU (Least Frequently Used)
LFU 알고리즘은 가장 적게 참조된 페이지를 교체하는 알고리즘입니다.<br>
<br>

## MFU (Most Frequently Used)
MFU 알고리즘은 LFU 알고리즘과 반대로 가장 많이 참조된 페이지를 교체하는 알고리즘입니다.<br>
 



