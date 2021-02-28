---
title : "[Spring] (2) Thymeleaf View파일 만들기"
excerpt: "Java / Spring"

categories:
  - Spring
tags:
  - Java
  - Spring
---
># __Thymeleaf View__
  
### - `Index.html` 정적페이지

![스프링사진#](../../../assets/images/spring/hello_spring3.PNG)

`resources/static/index.html`에 `index.html`을 올려두면 Welcome page 기능을 제공함.

### `Example`
```java
<!DOCTYPE HTML>
<html>
<head>
    <title>Hello</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
Hello
<a href="/hello">hello</a>
</body>
</html>
```
![스프링사진#](../../../assets/images/spring/hello_spring4.PNG)

`Spring`이 제공하는 Welcome Page 기능이다 다른 기능들을 보고싶으면 <https://spring.io/projects/spring-boot#learn> 을 참조하면된다.

### - `Thymeleaf` 템플릿 엔진사용