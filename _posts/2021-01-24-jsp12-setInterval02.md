---
layout: post
title: "자바스크립트 setInterval로 타이머 만들기"
categories: 자바스크립트
tags: 자바스크립트, javascript, setTimeout
---

#### setInterval로 타이머 만들기
시작, 종료, 리셋 기능이 있는 타이머랄까...?


```javascript
<form name='form1'>
  <input type="text" name='txt1' value="스톱워치" readonly>
  <input type="button" name='start' value="시작">
  <input type="button" name='end' value="종료">
  <input type="button" name='reset' value="리셋">
</form>

<script>
    var txt1 = document.form1.txt1;
    var start = document.form1.start;
    var end = document.form1.end;
    var reset = document.form1.reset;

    var n = 1;
    var timer = 0;

    start.onclick = function() {
        if(timer == 0) { //시작 버튼 중복으로 누를 수 없도록 제어
            timer = setInterval(function() {
                txt1.value = n;
                n++;
                //console.log(timer); 타이머는 고유번호는 1부터 시작
            }, 1000);
        }
    }//start.onclick

    end.onclick = function() {
        clearInterval(timer);
        timer = 0;
    }

    reset.onclick = function() {
        clearInterval(timer);
        txt1.value = "";
        n = 1;
    }
</script>
```

![jsp12_ex01](/image/jsp12_01.gif)
- 타이머가 중복으로 작동할 경우 속도가 빨라진다.
- 그래서! 시작 버튼을 중복으로 누를 수 없도록 timer변수에 setInterval을 넣은 점 유의!!
- **또 시작 버튼을 눌러도 타이머 고유 번호는 1이기 때문에 동작하지 않는다.**

<div class="myc1" id="c1"><span>💗 개발 공부하는 블로그입니다. 틀리거나 문제될게 있다면 코멘트 부탁드립니다. 👉👈</span></div>
