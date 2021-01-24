---
layout: post
title: "자바스크립트 setInterval"
categories: 자바스크립트
tags: 자바스크립트, javascript, setTimeout
---

# setInterval

- 정해진 시간이 되면 코드 호출을 반복
- setInterval(함수, 시간);
- 시간은 ms로 계산

#### 1. 3초 후에 텍스트창에 현재 시간 표시

```html
<form name='form1'>
  <label>시작을 누르면 3초 후 시간 표시</label>
  <input type="text" name='txt1' value="3초 후 시간 표시" width="230px">
  <input type="button" name='start' value="시작">
</form>
```

<form name='form1'>
  <input type="text" name='txt1' value="시작을 누르면 3초 후 시간 표시" style="width: 230px">
  <input type="button" name='start' value="시작">
</form>

```javascript
<script>
    var txt1 = document.form1.txt1;
    var start = document.form1.start;
    var time = new Date(); //시간 변수

    var n = 3;
    var timer; //전역변수

    start.onclick = function() {
        timer = 0;
        if(timer == 0) { //타이머가 0인 경우에만 타이머 실행
            timer = setInterval(function() {
              txt1.value = n; //텍스트 창에 보일 숫자, 1초마다 -1씩 감소
              n--;

                if(n < 0) { //숫자가 0보다 작은 순간 시간 표시
                    txt1.value = time.toLocaleTimeString();
                    clearInterval(timer); //타이머 종료
                    timer = 0;
                    n = 3;
                }

            }, 1000);

        }
    }//start.onclick

</script>
```
- 자바스트립트는 함수를 변수에 넣을 수 있다.
- 타이머들은 각각 고유번호를 가지고 있다.
- clearInterval(timer)를 하면 실행했던 타이머가 종료되는 것
- clearInterval 후 다시 타이머를 호출 할 경우 다른 고유번호를 가지고 있는 타이머가 호출된다.

![jsp11_ex01](/image/jsp11_01.gif)
