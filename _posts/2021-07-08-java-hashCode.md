---
title: "자바 hashCode"
excerpt: "자바 hashCode"

categories:
  - JAVA
tags:
  - [JAVA, hashCode]

permalink: /JAVA/hashcode/

toc: true
toc_sticky: true

date: 2021-07-08
last_modified_at: 2021-07-08
---


hashCode() 하면 equals()도 같이 세트로 자주 나옵니다.

equals는 이전 블로그 포스팅인 [equals와 == 차이](https://pkt369.github.io/java/equals/)를 참고하면 좋을 것 같습니다.
<br>
<br>

equals는 그럼 두 값을 비교할때 쓴다는 것을 알았습니다. 그럼 hashCode는 무엇일까요?

먼저 코드부터 보겠습니다.

![hashCode](https://user-images.githubusercontent.com/66049273/124847678-55c68100-dfd6-11eb-9b6d-895a402b6bfe.png)

위 코드는 String의 hashCode 입니다. 

한글자씩 가져와서 31을 곱하는 것을 볼수 있습니다. 여기서 알수있는 사실은 hashCode를 이용하면 정수의 숫자가 나온다는 것을 알 수 있습니다.

왜 **31**을  곱하는 걸까요?
<br>
<br>
<br>
31을 곱하는 이유는 홀수이자 소수이기 때문입니다. 만약 짝수를 곱하게 됐을때 오버플로우가 되었다면 값이 사라질수 있기 때문입니다. 

예를 들어 2를 곱하는 것은 왼쪽으로 shift 이동하는 것과 같기 때문에 int인 01111111111111111111111111111111 에 shift 이동하면 -1로 변하기 때문입니다.

또한 31의 이점은 곱셈을 시프트와 뺄셈의 조합으로 바꾸면 더 좋은 성능을 낼수 있습니다. (31 * i == (i << 5) - i)

하지만 요즘 VM은 자동으로 최적화를 하고 있습니다.
<br>
<br>
<br>
그러면 이런 궁금증이 생깁니다. '그럼 hashCode와 equals 는 같은 거 아닌가요?'

그렇지 않습니다.

밑에 코드는 hashCode를 이용하는 HashMap입니다.

```java
public class Main {
    public static void main(String[] args) {
        String a = "Z@S.ME";
        String b = "Z@RN.E";
        Map<String, Integer> map = new HashMap<>();
        map.put(a, 10);
        map.put(b, 20);
        System.out.println(a.equals(b));  // false
        System.out.println(a.hashCode()); //-1656719047
        System.out.println(b.hashCode()); //-1656719047
        System.out.println(map.get(a));   //10
        System.out.println(map.get(b));   //20
    }
}
```

위의 코드를 보면 서로 다른 스트링 객체인것을 알 수 있습니다.<br> 
서로 다른 값인데 같은 hashCode의 값을 가지고 있다. 즉, hashCode는 서로 다른 값을 가지고 있어도 같은 헤쉬코드가 나올수 있다는 것이다.
<br>
<br>
<br>
그럼 여기서 map은 hashCode로 키로 사용하지 않나요? 라는 질문이 나옵니다.<br>
hashCode는 값이 같은데 hashCode가 다르거나 반대로 hashCode는 같은데 값이 다른경우는 map은 다르다고 판단합니다.<br>
즉, map에서는 hashCode와 equals가 같아야 같은 키라고 인정되는 것 입니다.
<br>
<br>
<br>
정리하자면 hashCode는 **두객체가 같은 객체인지 확인하는 메소드** 이고, **같은 값이 나올수가 있기때문에 hashCode를 이용하는 hashMap에서는 equals와 같이 사용하여 판별한다** 입니다.















