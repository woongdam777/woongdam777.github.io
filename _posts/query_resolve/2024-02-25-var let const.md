---
title: var let const
author: w
date: 2024-02-25 16:20:00 +0800
categories: [CS 지식 쌓기, JAVA]
tags: [question, resolve]
---

## var let const 차이

JavaScript 변수 선언: var, let, const의 차이

JavaScript에서 변수를 선언할 때 사용
var, let, const

1. 변수란

변수는 정보를 저장하는 상자 같은 거
필요할 때마다 그 안에 정보를 넣거나 바꿀 수 있음

2. var, let, const는 무엇인가요?

JavaScript에서 변수를 만들 때 쓰는 특별한 단어들이에요.
var는 예전에 많이 썼지만, 요즘에는 거의 안 쓰여요.
let은 변수를 만들 때 쓰는데, 값을 바꿀 수 있어요.
const는 상수를 만들 때 쓰는데, 한 번 값을 넣으면 바꿀 수 없어요.

3. 변수의 스코프는 무엇인가요?

변수의 스코프는 변수가 어디서 사용될 수 있는지를 말해요.
var로 만든 변수는 함수 안에서는 어디서든 사용할 수 있어요.
그래서 가끔 복잡해질 수 있어요. 예를 들어, 함수 안에서 만든 변수가 함수 바깥에서도 쓰일 수 있어요. 이게 조금 혼란스럽죠?

4. let과 const의 블록 스코프

let과 const는 블록 스코프를 가지고 있어요. 블록은 중괄호 {}로 둘러싸인 부분을 말해요.
그래서 블록 안에서 만든 변수는 블록 바깥에서는 사용할 수 없어요. 이게 훨씬 더 깔끔하고 안전해 보이죠?

5. 마치며

JavaScript에서 변수를 만들 때는 let과 const를 사용하는 것이 좋아요. var는 좀 예전 방식이라서 잘 안 쓰이거든요.
변수의 스코프도 중요한데, let과 const는 블록 스코프를 가지고 있어서 더 안전하고 편리해요.
이제 여러분도 JavaScript 변수 선언에 대해 잘 알게 되었어요! 계속해서 공부하면 더 재미있는 것들을 만날 수 있을 거예요. 함께 열심히 공부해요!