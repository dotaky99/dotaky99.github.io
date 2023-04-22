---
title: 악성 파일에 사용된 WScript Object
author: dotaky99
date: 2023-03-05 16:31:00 +0900
categories: [Malware, Theory]
tags: [wscript, object, xmlhttp, stream]
render_with_liquid: false
---

### 1. ADODB.Stream
Microsoft ActiveX Data Objects(ADO) 라이브러리에서 제공하는 개체 중 하나. 파일을 읽고 쓰는데 사용된다. ADODB.Stream을 사용하면 파일을 바이너리 또는 텍스트 모드로 읽고 쓸 수 있다. 이 개체를 사용하면 파일의 일부분을 읽거나 쓸 수도 있다. 또한, 파일을 암호화하거나 압축도 가능하다.
ADODB.Stream은 주로 데이터베이스에서 사용된다. 예를 들어, 이미지나 문서와 같은 바이너리 데이터를 데이터베이스에 저장하거나, 데이터베이스에서 바이너리 데이터를 가져와 파일로 저장할 때 사용된다. 또한 ADODB.Stream을 사용하여 네트워크를 통해 전송되는 파일을 읽거나 쓸 수 있다.


### 2. MSXML2.XMLHTTP
Microsoft XML HTTP(XML Hypertext Transfer Protocol) 라이브러이에서 제공하는 개체 중 하나로, HTTP 요청을 보내고 받는데 사용된다. XMLHTTP 개체를 사용하면 서버와 상호작용하여 웹 페이지, XML 데이터 또는 기타 웹 서비스를 가져올 수 있다. 또한, JavaScript를 사용하여 동적으로 웹 페이지를 업데이트하거나, 웹 서비스와 통신하여 데이터를 가져와서 애플리케이션에서 처리할 수도 있다.
일반적으로 Ajax(Asynchronous JavaScript and XML) 애플리케이션에서 사용된다. Ajax는 비동기식 웹 애플리케이션을 구축하기 위한 기술로, 브라우저와 서버 간에 비동기식으로 데이터를 교환하거 페이지를 업데이트하는데 사용된다.


### 3. WScript.Shell
Microsoft Windows 스크립팅 호스트에서 제공하는 개체 중 하나로, 컴퓨터의 운영 체제와 상호작용하는데 사용된다.
해당 개체를 사용하면 아래와 같은 작업을 수행할 수 있다.

1. 파일 및 폴더 생성, 복사, 이동 및 삭제
2. 운영 체제 환경 변수 읽기 및 설정
3. 레지스트리 값 읽기 및 설정
4. 프로그램 실행 및 관리
5. 사용자 입력 대기 및 팝업 메시지 표시
6. 네트워크 드라이브 연결 및 해제

WScript.Shell은 주로 Windows 스크립트 파일이나 배치 파일에서 사용된다. 이 개체를 사용하면 자동화 작업이나 시스템 관리 작업을 자동화 할 수 있다.