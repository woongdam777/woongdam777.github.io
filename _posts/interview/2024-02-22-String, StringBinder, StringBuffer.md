---
title: String, StringBinder, StringBuffer
author: w
date: 2024-02-22 18:40:00 +0800
categories: [interview, 면접]
tags: [interview, project, tip]
img_path: /assets/img/post/
---

## String, StringBinder, StringBuffer
Java에서 문자열을 다루는 클래스

### String
String 클래스는 불변(immutable)한 문자열을 나타냅니다. 한 번 생성된 문자열은 변경할 수 없습니다.
문자열이 한 번 생성되면 그 값을 변경할 수 없기 때문에, 문자열 연산이 많이 필요한 경우에는 성능에 영향을 줄 수 있습니다.
불변성은 스레드 안전(thread-safe)하며, 여러 스레드가 동시에 String 객체에 접근할 수 있습니다.
예시: String str = "Hello";


### StringBinder
StringBuilder 클래스는 가변(mutable)한 문자열을 나타냅니다. 즉, 문자열을 변경할 수 있습니다.
문자열을 변경할 때마다 새로운 문자열을 생성하는 것이 아니라, 기존의 문자열을 변경합니다. 따라서 연결된 문자열을 변경하는 작업이 효율적입니다.
스레드 안전하지 않습니다. 따라서 단일 스레드 환경에서 사용하는 것이 적합합니다.
```java
StringBuilder sb = new StringBuilder();
sb.append("Hello");
sb.append(" ");
sb.append("world");
String result = sb.toString(); // "Hello world"
```


### StringBuffer
StringBuffer 클래스도 StringBuilder와 비슷한 역할을 합니다. 가변(mutable)한 문자열을 나타냅니다.
StringBuffer는 StringBuilder와 유사하지만, 스레드 안전(thread-safe)한 점이 다릅니다. 즉, 여러 스레드에서 안전하게 사용할 수 있습니다.
StringBuffer는 스레드 간 동기화를 지원하기 때문에, 멀티 스레드 환경에서 사용할 때 안전합니다.
일반적으로는 StringBuilder를 사용하는 것이 성능 면에서 더 좋습니다. 그러나 멀티 스레드 환경에서는 StringBuffer를 사용하는 것이 안전합니다.
```java
StringBuffer sb = new StringBuffer();
sb.append("Hello");
sb.append(" ");
sb.append("world");
String result = sb.toString(); // "Hello world"

```

String은 불변한 문자열을 다루며, StringBuilder와 StringBuffer는 가변한 문자열을 다룹니다. 그리고 StringBuilder는 단일 스레드 환경에서, StringBuffer는 멀티 스레드 환경에서 사용하는 것이 적합합니다.

### [면접 질문 모음](/posts/면접-질문-모음)