---
layout: post
title: "자바스크립트 setTimeout"
categories: 자바스크립트
tags: 자바스크립트, javascript, setTimeout
---

# setTimeout

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


#### 2. 3초 후에 텍스트 창에 현재시간 표시

```html
<form name="form1">
  <input type="text" name="txt1" value="3초 후 현재 시간 표시" onfocus="this.value=''">
</form>
```

```javascript
<script>
  var txt1 = document.form1.txt1;
  var now = new Date();

  setTimeout(function() {
    txt1.value = now.toLocaleTimeString();
  }, 3000);
</script>
```

![jsp10_setTimeout_02](/image/jsp10_02.gif)
