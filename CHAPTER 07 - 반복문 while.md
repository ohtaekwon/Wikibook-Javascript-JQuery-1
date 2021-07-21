# _CHAPTER 07 - 반복문 while_

<br>

## :speaker: INTRO

- 반복처리를 할 떄 주로 for문을 많이 사용하지만, 
- 무한반복 처리를 하는 경우에는 while문을 사용하면 좀 더 쉽게 구문을 표현할 수 있다.

<br>

:pushpin:***조건문과 반복문***

- for
- while

<br>

## :information_source:INDEX

|     Lesson      |               Content                |
| :-------------: | :----------------------------------: |
| ***Lesson 01*** |           **while문 소개**           |
| ***Lesson 02*** |        **for와 while 차이점**        |
| ***Lesson 03*** | **while문에서 continue문과 break문** |
| ***Lesson 04*** |               **미션**               |

<br>

---

<br>

## :pencil:_Lesson 01. while문 소개_

### _01. while문이란?_

- 예를 들어 패스워드가 맞을 때까지 사용자 입력을 받는 예제를 만든다고 할 때,
- for문을 이요해 구현한다면 다음과 같이 할 수 있다.

#### :memo:_예제 01)_ 패스워드가 1234이면 "환영합니다." 메시지를 출력한 후 멈추고 그렇지 않으면 "패스워드를 잘 못 입력 했습니다."를 출력한 후 계속 입력 받아 보시오.

```javascript
for(var i=0; i<10000; i++){
    var value = window.prompt("패스워드를 입력해주세요");
    value = parseInt(value);
    if(value==1234){
        alert("환영합니다.");
    }else{
        alert("패스워드를 잘 못 입력했습니다. 다시 입력해주세요");
    }
}
```

- 10000번 정도는 무한 반복처럼 보이지만, 언젠가는 끝이 날 수 있다.
- 이처럼 **for문의 주 용도는 정해진 횟수만큼 특정구문을 반복하는 것**이다.

<br>

#### :page_with_curl: _메모 :_ for문을 다음 처럼 이용해 무한 반복하는  방법도 있다.

```javascript
for(;;){
    var value = window.prompt("패스워드를 입력해주세요");
    value = parseInt(value);
    if(value==1234){
        alert("환영합니다.");
    }else{
        alert("패스워드를 잘 못 입력했숩니다. 다시 입력해주세요.");
    }
}
```

<br>

:ballot_box_with_check: **while : 소스**

```javascript
while(true){
    var value = window.prompt("패스워드를 입력해주세요");
    value = parseInt(value);
    if(value==1234){
        alert("환영합니다.");
    } else {
        alert("패스워드를 잘못 입력했습니다. 다시 입력해주세여.")
    }
}
```

- 이처럼 특정 구문을 무한 반복을 해야 하는 경우에 for문 대신 while 문이 더 유용하다.

<br>
