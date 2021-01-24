---
layout: post
title: "자바스크립트 setTimeout"
categories: 자바스크립트
tags: 자바스크립트, javascript, setTimeout
---

### setTimeout

- 정해진 시간이 되면 코드를 호출하고 종료
- setTimeout(함수, 시간);
- 시간은 ms로 계산

#### 1. 1초 후에 alert창과 배경색이 바뀌도록 설정

```javascript
<script>
  setTimeout(fuction() {
    alert("Hello!")
  }, 1000); //1초

  setTimeout(function() {
    document.body.bgColor="red";
  }, 1000);
</script>
```

![jsp10_setTimeout_01](/image/jsp10_01.gif)
