---
title: "내부 단편화, 외부 단편화"
excerpt: "메모리 내부 단편화, 외부 단편화란"

categories:
  - CS
tags:
  - [CS, 내부단편화, 외부단편화]

permalink: /CS/cs-fragmentation/

toc: true
toc_sticky: true

date: 2023-04-30
last_modified_at: 2023-04-30
---

## 내부단편화
내부 단편화는 주기억장치 (RAM) 내 사용자 영역이 프로그램보다 커서 프로그램의 사용 공간을 할당 후 <strong>남게되는 현상</strong>을 말합니다.<br>
![내부단편화](/assets/images/posts_img/cs-fragmentation/내부단편화.png)
<br>
<br>

## 외부단편화
외부 단편화는 주기억장치 (RAM) 내 총 메모리는 충분하지만 <strong>하나의 페이지보다 큰 영역</strong>을 말합니다. <br>
즉, 남아 있는 공간이 연속적이지 않아 생기는 문제입니다.<br>
![외부단편화](/assets/images/posts_img/cs-fragmentation/외부단편화.png)
<br>
<br>

### 외부단편화 해결방법 - 압축
외부 단편화를 해결하기 위해서 압축 기법을 사용하고 있습니다. 압축 기법은 주기억장치(RAM) 내 분산되어 있는 단편화된 공간들을 통합하여 <strong>하나의 커다란 빈 공간을 만드는 작업</strong>을 의미합니다.<br>
![외부단편화압축기법](/assets/images/posts_img/cs-fragmentation/외부단편화압축기법.png)
<br>

위 기법을 통해서 기존에 할당할 수 없었던 프로세스를 할당할 수 있게 됩니다.


