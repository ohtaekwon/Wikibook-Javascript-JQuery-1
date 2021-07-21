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

### _02. while문은 이럴 때 사용_

- while문은 주로 다음과 같은 경우에 많이 사용한다.
  - 무한반복 처리
  - 파일 읽기
  - 파일 쓰기
  - 파일 전송
  - DB 데이터 출력하기
- 자바스크립트에서 파일을 읽고 쓰는 작업을 거의 하지는 않지만, Java와 PHP같은 일반 프로그래밍에서는 위의 경우에 for문보다는 while문을 주로 사용한다.

<br>

### _03. 사용법_

##### :pencil: 문법

```javascript
while(조건식){
    실행구문;
    . . . . .
}
```

##### :pencil: 설명

*​**:one: 조건식***

- while문에서는 for문과 달리 초깃값이나 증감 처리를 하는 부분이 없다. 
  - 오직 조건식 부분만 있다.
  -  while문과 for문과의 차이점을 충분히 알 수 있다.

<br>*​**:two: 실행구문***

- 조건식이 참일 동안 반복해서 실행되는 구문

<br>

### _04. 예제_

#### :memo:_예제 02)_ 무인도 탈출 게임

- 3이 나올 때까지 주사위를 계속 던지는 예제를 만들어라.
- (단, 다음과 같이 출력이 되도록 하여라.)

***출력결과***

```
1번째 나온 숫자 = 6
2번째 나온 숫자 = 6
3번째 나온 숫자 = 1
4번째 나온 숫자 = 5
5번째 나온 숫자 = 4
6번째 나온 숫자 = 3
탈출
```

:ballot_box_with_check: **풀이 전 코드 : 소스**

```html
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html"; cahrset="UTF-8">
        <title></title>
        <script type ="text/javascript" src="../../libs/jquery-1.11.0.min/js"></script>
        <script type = "text/javascript">
            
            $(document).ready(function(){
                $("#btnStart").click(function(){
                    // 여기에 소스를 입력하여라.
                })
            })
        </script>
    </head>
    <body>
        <button id="btnStart">주사위 던지기</button>          
    </body>
</html>
```

<br>

#### :page_with_curl: _힌트 :_ 1에서 6 랜덤 숫자 만들기

```javascript
var num = parseInt(Math.random()*6)+1;
```

`Math.random()` 함수는 **0 이상 1 미만의 구간**에서 근사적으로 균일한(approximately uniform) 부동소숫점 의사난수를 반환하며, 이 값은 사용자가 원하는 범위로 변형할 수 있다. 난수 생성 알고리즘에 사용되는 초기값은 구현체가 선택하며, 사용자가 선택하거나 초기화할 수 없다.

- 반환값
  - 0 이상 1 미만의 부동소숫점 의사 난수.
  - 0.0 <= Math.random() < 1.0
- 주사위 하나를 뽑는 연산식 입니다.
  - int num = (int) (Math.random() * 6) +1;

<br>

:ballot_box_with_check: **풀이 : 소스**

```html
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html"; cahrset="UTF-8">
        <title></title>
        <script type ="text/javascript" src="../../libs/jquery-1.11.0.min/js"></script>
        <script type = "text/javascript">
            $(document).ready(function(){
                $("#btnStart").click(function(){
                    // 여기에 소스를 입력하여라.
                    var count = 0;
                    while(true){
                        count++;
                        var num = parseInt(Math.random()*6)+1;
                        console.log(count+"번 째 나온 숫자 =" + num);
                        
                        if(num==3){
                            console.log("탈출");
                            break;
                        }
                    }
                })
            })
        </script>
    </head>
    <body>
        <button id="btnStart">주사위 던지기</button>          
    </body>
</html>
```

<br>

---

<br>

## :pencil:_Lesson 02. for와 while 차이점_

### _01. 사용 분야_

- while, for 모두 같은 반복문이지만, 사용 용도가 완전히 다르다

<br>

#### **for문 사용 분야** :vs:**​ while문 사용분야**

- **for문 사용 분야**
  - 반복 횟수가 정해진 경우
  - 배열과 함께 주로 많이 사용
- **while문 사용 분야**
  - 무한 루프나 특정 조건에 만족할 때까지 반복해야하는 경우
  - 주로 파일 읽고 쓰기에 많이 사용

<br>

### _02. while문을 for문처럼 사용하는 경우_

- 일반적으로 for문 대신 while문으로, while문 대신 for문을 사용할 수 있다.

<br>

#### **for문을 사용한 경우** :vs:**​ while문을 사용한 경우**

- **for문을 사용한 경우**

```javascript
for(초깃값; 조건식; 증감){
    실행구문;
}
```

- **while문을 사용한 경우**

```javascript
초깃값;
while(조건식){
    실행구문;
    증감;
}
```

<br>

- 예를 들어 1에서 10을 출력하는 예제를 만드는 경우 for와 while을 이용하면 다음과 같이 풀 수 있다. 

<br>

#### **for문 문법** :vs:**​ while문 문법**

- **for문 문법**

```javascript
for(var i=0l i<=10; i++){
    document.write("i = " + i, "<br>");
}
```

- **while문 문법**

```javascript
var i=1;
while(i<=10){
    document.write("i = " + i, "<br>");
    i++;
}
```

<br>

---

<br>

## :pencil:_Lesson 03. while문에서 continue문과 break문_

### _01. continue문_

##### :pencil: 문법

```javascript
while(조건식){
    실행구문;
    . . . . 
    continue;
    . . . .
}
```

<br>

- ***continue문은 for문과 while문에서 똑같이 동작한다.***
  - continue문을 만나면 continue문 이후의 구문을 실행하지 않고 바로 while문 위쪽으로 올라가 조건식을 실행한다.

<br>

#### :memo:_예제 01)_ 다음 구문을 실행하면 화면에는 어떤 값이 출력될까?

```javascript
var i=1;
while(i<=10){
    i++;
    continue;
    
    document.write(i+"<br>");
}
document.write("최종 i= "+i+"<br>");	//-------------(※1)

```

- **실행결과**
  - 최종 i= 11
- **설명**
  - while문의 루프는 10번 실행되기 하지만, continue문이 document.write() 앞에 있어서 화면에 출력되는 건 전혀 없다.
  - 루프가 모두 끝난 후 `※1` 내용이 실행돼 i값이 11이 출력된다. 

<br>

### _02. break문_

##### :pencil: 문법

```javascript
while(조건식){
    . . . .
    break;
    . . . .
}
```

- 실행구문 중 break문을 만나면 while문은 그대로 정지되며, while문의 루프를 빠져나온다.
- 즉, while문을 강제로 빠져 나오고 싶을 때 사용하기는 명령어가 break문이다.

<br>

#### :memo:_예제 02)_ 다음 구문을 실행하면 화면에는 어떤 값이 출력될까?

```javascript
var i=1;
while(i<=10){
    break;
    i++;    
    document.write(i+"<br>");
}
document.write("최종 i= "+i+"<br>");
```

- **실행결과**
  - 최종 i = 1
- **설명**
  - for문뿐 아니라 while문의 루프에서 break문이 실행되면, 반복문 루프를 즉시 벗어나게 된다.
  - 그래서 실행결과는 i=1이 출력된다.
