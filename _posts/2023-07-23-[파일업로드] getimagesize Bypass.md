---
title: [파일업로드] getimagesize Bypass
date: 2023-07-23 20:16:00 +0900
categories: [vulnerability, File upload]
tags: [php, incident, bypass, file_upload]
render_with_liquid: false
---

PHP 파일 업로드 취약점 기록.

getimagesize의 반환값은 배열로 반환해준다. 아래 정보를 참고 바란다.

EX 1)

    [0] => 756 // width
    [1] => 676 // height
    [2] => 3 // 이미지 타입 구분 번호
    [3] => width="756" height="676" // style
    [bits] => 8 // 비트
    [mime] => image/png // 이미지 타입

만약 jpg 사진 파일만 업로드 가능하게 한다면 아래처럼 코드를 기본적으로 작성할 수 있다.

업로드 소스코드
```php
$File = getimagesize('업로드 파일');

if($File[2] == 'jpg'){
  이미지 업로드
}
else{
  에러 코드 작성
}
```

악성파일 예시는 아래와 같다.
```php
<?php
phpinfo();
?>
```

악성 파일을 위 코드로 실행하면 소스코드에서 필터링 되어 업로드가 되지 않음.

하지만 아래처럼 GIF89a를 앞에 시그니쳐로 붙여주면 우회가 된다.

```php
GIF89a<?php
phpinfo();
?>
```

즉, 안전한 파일 업로드 소스코드를 구현하려면 PHP를 최신버전으로 구축해야하며, 업로드되는 폴더는 실행 권한을 제거해야 한다.
또한, 업로드되는 파일 이름 난수화, 텍스트 이미지화 등 다양한 방법이 존재할 수 있다. 