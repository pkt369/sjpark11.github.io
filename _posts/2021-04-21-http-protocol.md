﻿---
title: "HTTP프로토콜"
excerpt: "HTTP프로토콜"

categories:
  - CS
tags:
  - [CS]

permalink: /CS/http-protocol/

toc: true
toc_sticky: true

date: 2021-04-21
last_modified_at: 2021-04-21
---

HTTP 프로토콜이란

HTTP(Hypertext Transfer Protocol)는 인터넷상에서 데이터를 주고 받기 위한 서버/클라이언트 모델을 따르는 프로토콜입니다.

직역하면 하이퍼텍스트 문서를 전달하기 위한 규약입니다.

웹브라우저에서 HTTP를 붙이는 것은 http 프로토콜을 통신을 하겠다는 선언입니다.

<BR>
<br>

### 작동방식
---
HTTP는 서버 / 클라이언트 모델을 따릅니다.

클라이언트에서 요청(request)를 보내면 서버는 요청을 처리해서 응답(response)합니다.

응답하는 순간 요청을 끊어버립니다

<br>
<br>

### HTTP Request(요청)
----------
![request](https://user-images.githubusercontent.com/66049273/115560768-ddfa8b80-a2ef-11eb-8242-d8f4fdc4296e.png)
참조 : [https://developer.mozilla.org/ko/docs/Web/HTTP/Overview](https://developer.mozilla.org/ko/docs/Web/HTTP/Overview)

request는 크게 3부분으로 구성됩니다.

### Start line

- Http Method : GET, POST, PUT, DELETE, OPTIONS 등등
- Request target : 해당 request가 전송되는 목표 URI (/login)
- Http Version : http/1.1

  

### Headers

-  request에 대한 추가정보를 담고 있는 부분
- key: value로 이루어져 있다.
- general headers, request headers, entity headers로 3개로 나누어져 있다.

  

### Body

- 해당 request의 실제 메세지/내용, body가 없을 수도 있다.

```http
POST /login HTTP/1.1
Accept: application/json
Accept-Encoding: gzip, deflate
Connection: keep-alive
Content-Length: 83
Content-Type: application/json
Host: naver.com
{
	"id": "id_11234",
	"password": "pasword",
	"status": "user"
}
```

<br>
<br>

### HTTP Response(응답)
---
![response](https://user-images.githubusercontent.com/66049273/115561318-6a0cb300-a2f0-11eb-8fc6-b4f15699c6e6.png)
참조 : [https://developer.mozilla.org/ko/docs/Web/HTTP/Overview](https://developer.mozilla.org/ko/docs/Web/HTTP/Overview)

<br>


Response와 마찬가지로 3가지로 이루어져 있습니다.

### Status Line

Response의 상태를 간략하게 나타내주는 부분이고 3부분으로 구성되어 있습니다.

-   HTTP 버젼
-   Status code : 응답상태를 나타내는 코드. 숫자로 되어 있는 코드. (예를들어 200)
-   Status Text : 응답 상태를 간략하게 나타내는 부분.

```http
HTTP/1.1 404 Not Found
```

  

### Headers

-   Response의 headers와 동일합니다.
-   Response에서만 사용되는 header 값들이 존재합니다. (User-Agent 대신 Server 헤더가 사용됩니다.)

  

### Body

-   Response의 Body와 일반적으로 동일하며 Request와 마찬가지로 모든 response가 body가 있지 않다.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA2NDUxMjM1Ml19
-->