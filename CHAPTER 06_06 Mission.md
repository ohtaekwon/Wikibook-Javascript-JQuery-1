# _CHAPTER 06 Mission_ 



## :name_badge:_Lesson 06. 미션_

#### :ballot_box_with_check:_미션 01)_ for문 활용하기

- 3단을 출력하는 코드이다. for문으로 간결하게 만들어라

:ballot_box_with_check: **풀이 전 코드 : 소스**

```javascript
var dan = 3;
document.write(dan+"*1="+(dan*1)+"<br>");
document.write(dan+"*2="+(dan*2)+"<br>");
document.write(dan+"*3="+(dan*3)+"<br>");
document.write(dan+"*4="+(dan*4)+"<br>");
document.write(dan+"*5="+(dan*5)+"<br>");
document.write(dan+"*6="+(dan*6)+"<br>");
document.write(dan+"*7="+(dan*7)+"<br>");
document.write(dan+"*8="+(dan*8)+"<br>");
document.write(dan+"*9="+(dan*9)+"<br>");
```

- **설명**
  - 반복문을 활요앻서 중복 코드를 처리할 수 있다.
  - 먼저, 코드에서 변경되는 부분과 변경 되지 않는 부분을 찾는다.
  - 변경되지 않은 부분은 그대로 루프의 구문으로 넣어주고
  - 변경되는 부분은 주위에 있는 변수의 도움을 받든 아니면 신규로 변수를 만들어야 하는 대상이 된다.

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/06.06_1.png?raw=true)

