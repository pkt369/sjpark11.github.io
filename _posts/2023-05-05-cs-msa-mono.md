---
title: "MSA 와 MONO"
excerpt: "MicroSoft Architecture 와 MONO repo에 대하여"

categories:
  - CS
tags:
  - [MSA, MONO]

permalink: /CS/msa-mono/

toc: true
toc_sticky: true

date: 2023-05-05
last_modified_at: 2023-05-05
---

## MONO (monolithic)

![monolithic](/assets/images/posts_img/msa-mono/monolithic.png) <br>
mono 는 위의 그림과 같이 <strong>하나</strong>라는 의미를 가지고 있습니다.<br>
<br>
monolithic 은 mono 또는 mono repo 라고도 부르며 하나의 큰 프로젝트로 관리하는 것을 의미합니다.<br>
하나의 프로젝트로 관리가 되기때문에 배포 및 관리가 간편했고, 여러 애플리케이션이 외부 통신없이 내부 데이터로 서로 통신할 수 있었습니다.<br>
<br>
하지만 mono repo 의 경우 프로젝트가 커지게되면 관리가 어려워질뿐더러 다음과 같은 단점이 생깁니다.<br>
- 빌드/테스트의 시간이 늘어납니다.
- 하나의 애플리케이션만 수정해도 다시 전체 배포가 필요합니다.
- 하나의 서비스가 트래픽이 몰려 죽을 경우 다른 서비스에 영향을 줍니다.
<br>


MSA 가 나오기 전까지는 프로젝트들이 많이 무거웠습니다. 하지만 MSA 가 나오면서 위와 같은 단점들을 상쇄시켜줄 수 있게 되었습니다.
<br>
<br>

## MSA (MicroSoft Architecture)
MSA 는 Mono 와 달리 하나의 컴포넌트당 하나의 저장소를 사용하는 것입니다. <br>
컴포넌트 별로 각 서비스를 진행하면서 다음과 같은 장점이 생깁니다.<br>

- 빌드/테스트 시간이 빠릅니다.
- 하나의 서비스가 중단되어도 다른 서비스에는 영향이 없습니다.
- 확장에 용이합니다.

<br>
위처럼 장점도 있지만 단점도 존재합니다. <br> 

- API 를 이용해야하기 때문에 통신하는 시간이 필요합니다. (시간이 오래 걸립니다.)
- 여러개의 컴포넌트를 관리해야되기 때문에 유지보수 비용이 늘어납니다.
<br>

단점도 존재하지만 장점이 많아 많은 기업에서 사용하고 있는 아키텍처입니다. <br>
대규모 프로젝트 또는 확장이 필요한 프로젝트의 경우 MSA 를 사용해보는 것은 어떨까요?







