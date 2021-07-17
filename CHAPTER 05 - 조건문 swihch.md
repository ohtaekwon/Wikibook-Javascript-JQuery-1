# _CHAPTER 05 - 조건문 swihch_

<br>

## :speaker: INTRO

- `if`는 `switch`를 대신해서 사용할 수 있지만 `switch`는 오직 특별한 경우에만 `if`대신 사용할 수 있다.

<br>

## :information_source:INDEX

|     Lesson      |        Content         |
| :-------------: | :--------------------: |
| ***Lesson 01*** |   **switch문 소개**    |
| ***Lesson 02*** | **if와 switch 차이점** |
| ***Lesson 03*** |        **미션**        |

<br>

## :pencil:_Lesson 01. swtich_

### _01. switch문이란?_

- **경품 추첨기 요구사항:**
  - 번호가 1번이면 냉장고
  - 번호가 2번이면 TV
  - 번호가 3번이면 세탁기
  - 나머지는 꽝!

***EX) if를 사용하여 구현하면***

```javascript
if(경품번호==1){
    냉장고 당첨;
}
else if(경품번호==2){
    TV 당첨;
}
else if(경품번호==3){
    세탁기 당첨;
}
else{
    꽝;
}
```

- 이렇게하면 경품번호가 많아질시에 `else if`는 증가할 것이며 다소 복잡해질 수 있다.
- 자바스크립트에서 이런 다중 조건 처리를 좀더 깔끔하고 읽기 쉽게 만드는 코드로 `switch`를 사용한다.

| if를 사용할 경우                                             | switch를 사용할 경우                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| if(경품번호==1){<br />     냉장고 당첨;<br />}<br />else if(경품번호==2){<br />     TV당첨;<br />}<br />else if(경품번호==3){<br />     세탁기당첨;<br />}<br />else {<br />     꽝입니다.;<br />} | switch(경품번호){<br />      case 1:<br />              냉장고 당첨;<br />               break;<br />      case 2 :<br />               TV당첨;<br />               break;<br />       case 3:<br />               세탁기 당첨;<br />                break;<br />        default;<br />               꽝;<br />} |

- 정리하자면 `switch`는 `if`와 같은 조건문 중 하나이다.
- `switch`는 주로 여러 개의 조건을 처리해야 하는 복잡한 다중 `if ~else`를 대신하여 사용한다.
- `switch`를 이용하면 경품 추첨기 코드를 `if`를 사용할 때보다 읽기 쉬운(가독성있는) 코드로 작성할 수 있다.

<br>

### _02. 사용법_

- 문법

```javascript
switch(변수 또는 값){
    case 값1 :
        실행구문1;
        break;
    case 값2 :
        실행구문2
        break;
    case 값3 :
        실행구문3;
        break;
        .....
    default :
        모든 조건이 일치하지 않을 때 실행되는 구문;
}
```

- `if`와 `switch`를 비교하면 같이 문법만 다를 뿐 조건과 실행구문은 똑같다.

<br>

**:one: 조건식**

- if 에서는 조건식을 `if(변수==값)`를 사용해서 처리하는 
- 반면, switch에서는 `switch(변수) case`값을 사용한다.
  - ***switch의 변수 또는 식의 값이 case에 선언된 값과 같은 해당 실행구문이 실행된다.***

<br>

**:one: case ~ break**

- if 에서는 `{}`이용해 실행구문 영역을 지정하는 반면 switch는 `case ~ break`문을 이용한다.
- break문을 만나면 `switch구문`에서 벗어난다.

<br>

**:one: default**

- 조건이 모두 일치하지 않은 경우 이 영역에 있는 구문이 실행된다.

<br>

### _03. 예제_

#### :memo:_예제 01)_ if문으로 되어 있는 구문을 switch문으로 변경하여라.

:white_check_mark: **if문** 

```javascript
var luckyValue = window.prompt("행운의 번호를 입력하세요");

luckyValue = parseInt(luckyValue);

if(luckyValue==3){
    document.write("당첨! 냉장고<br>");
}
else if(luckyValue==2){
    documnet.wirte("당첨! 세탁기<br>");
}
else if(luckyValue==1){
    document.write("당첨! TV<br>");
}
else{
    document.writhe("꽝입니다.<br>")
}
```

:white_check_mark: **switch문** 

```javascript
var luckyValue = window.prompt("행운의 번호를 입력하세요");

luckyValue = parseInt(luckyValue);

switch(luckyValue){
    case 3 :
        document.write("당첨! 냉장고<br>");
        break;
    case 2 :
        document.write("당첨! 세탁기<br>");
        break;
    case 1 :
        document.write("당첨! TV<br>");
        break;
    default :
        document.write("꽝입니다. <br>");
}
```

- ***switch를 이용하면 다중 조건 처리를 좀더 깔끔하고 가독성있게 처리할 수 있다.***

<br>

#### :memo:_예제 02)_ break문 테스트

1. ***"3"이 입력되면 화면에 출력되는 값은?***
2. ***"2"가 입력되면 화면에 출력되는 값은?***
3. ***"1"이 입력되면 화면에 출력되는 값은?***

```javascript
var luckyValue = window.prompt("행운의 번호를 입력하세요");

luckyValue = parseInt(luckyValue);

switch(luckyValue){
    case 3 :
        document.write("당첨! 냉장고<br>");
        break;
    case 2 :
        document.write("당첨! 세탁기<br>");
    case 1 :
        document.write("당첨! TV<br>");
    default :
        document.write("꽝입니다. <br>");
}
```

- **답변**
  1. 당첨! 냉장고
  2. 당첨! 세탁기
     당첨 ! TV
     꽝입니다.
  3. 당첨! TV
     꽝입니다.

- **설명**
  - ***switch에서 해당 조건에 맞는 case의 실행구문이 실핼됭 후 break구문이 없다면 계속해서 다음 case내용이 실행된다.***

<br>

## :pencil:_Lesson 02. if와 swtich의 차이점_

- if 내용을 모두 switch로 변경할 수 없으며, 오직 단 한가지 조건이 만족하는 경우에만 if 대신 switch를 사용할 수 있다.
- 참고로 if는 제약없이 사용이 가능하다.

<br>

### _01. if를 switch로 변경할 수 없는 경우?_

- if 구문 중 조건식에 `>` , `<` , `>=` , `<=` , `!=`와 같은 비교 연산자를 사용한 경우는 switch로 변경할 수 없다.

:one: **if를 사용한 경우 ** 

```javascript
if(변수>값1){
    실행구문1;
}else if(변수>값2){
    실행구문2;
}else if(변수>값3){
    실행구문3;
}else if(변수>값4){
    실행구문4;
}
```

:two: **switch를 사용한 경우 ** 

```javascript
switch(변수){
    case 변수>값1 :
        실행구문1;
        break;
    case 변수>값2 :
        실행구문2;
        break;
    case 변수>값3 :
        실행구문3;
        break;
    case 변수>값4 :
        실행구문4;
        break;
}
```

- 위의 식은 불가능하다.

<br>

### _02. if를 switch로 변경할 수 있는 경우?_

- if 구문 중 조건식이 특정 값과 일치하는 경우`==`만 switch를 사용할 수 있다.

:one: **if를 사용한 경우 ** 

```javascript
if(변수==값1){
    실행구문1;
}else if(변수==값2){
    실행구문2;
}else if(변수==값3){
    실행구문3;
}else if(변수==값4){
    실행구문4;
}
```

:two: **switch를 사용한 경우 ** 

```javascript
switch(변수){
    case 값1 :
        실행구문1;
        break;
    case 값2 :
        실행구문2;
        break;
    case 값3 :
        실행구문3;
        break;
    case 값4 :
        실행구문4;
        break;
}
```

<br>

