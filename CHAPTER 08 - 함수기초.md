# _CHAPTER 08 - 함수기초_

<br>

## :speaker: INTRO

<br>

## :information_source:INDEX

|     Lesson      |             Content             |
| :-------------: | :-----------------------------: |
| ***Lesson 01*** |          **함수 소개**          |
| ***Lesson 02*** |    **가장 쉬운 함수 만들기**    |
| ***Lesson 03*** |   **지역 변수 vs. 전역변수**    |
| ***Lesson 04*** | **매개변수가 있는 함수 만들기** |
| ***Lesson 05*** |  **리턴값이 있는 함수 만들기**  |
| ***Lesson 06*** |  **함수이름 만들 때 주의사항**  |
| ***Lesson 07*** |            **미션**             |

<br>

---

<br>

## :pencil:_Lesson 01. 함수 소개_

- 함수는 일종의 `포장기술`이다. 특정 기능을 하는 구문의 집합을 재사용하기 위해 포장하기나 그룹을 구분하기 위해 묶을 때 주로 사용하는 개념이다.

<br>

### _01. 함수는 이럴 때 사용_

#### :memo:_예제 01)_ 당신의 이름을 다음과 같이 5번 출력해 보시오.

##### :computer: 출력결과

```
1.OHTAEKWON
2.OHTAEKWON
3.OHTAEKWON
4.OHTAEKWON
5.OHTAEKWON
```

<br>

##### :pencil: 풀이01) 일반적인 경우

```javascript
document.write("1. OHTAEKWON<br>");
document.write("2. OHTAEKWON<br>");
document.write("3. OHTAEKWON<br>");
document.write("4. OHTAEKWON<br>");
document.write("5. OHTAEKWON<br>");
```

##### :pencil: 설명

- 이 코드의 단점은 프로그래밍했다는 느낌이 아니며, 반복횟수가 많아 진다면 변경의 어려움이 생긴다.

<br>

##### :pencil: 풀이01) 반복을 활용할 경우

- 반복문을 활용하면 코드를 재사용할 수 있을 뿐만 아니라 유지보수가 좋다.

```javascript
for(var i=1; i<=5; i++){
    document.write(i+". OHTAEKWON<br>");
}
```

##### :pencil: 설명

- 만약 반복 횟수를 열 번으로 늘리고 싶다면 5를 10으로 변경만 해주면 된다.

<br>

#### :memo:_예제 02)_ "프론트엔드", "자바스크립트", "오태권" 이름을 다섯 번씩 출력.

##### :computer: 출력결과

```
1.프론트엔드
2.프론트엔드
3.프론트엔드
. . . .
5.프론트엔드
1.자바스크립트
2.자바스크립트
3.자바스크립트
. . . . .
5.자바스크립트
....
5. 오태권
```

<br>

##### :pencil: 풀이01) 반복문을 활용할 경우

:ballot_box_with_check: **풀이 01 : 소스**

```javascript
for(var i=1; i<=5; i++){
    document.write(i+". 프론트엔드<br>");
}
for(var i=1; i<=5; i++){
    document.write(i+". 자바스크립트<br>");
}
for(var i=1; i<=5; i++){
    document.write(i+". 오태권<br>");
}
```

```
1. 프론트엔드
2. 프론트엔드
3. 프론트엔드
4. 프론트엔드
5. 프론트엔드
1. 자바스크립트
2. 자바스크립트
3. 자바스크립트
4. 자바스크립트
5. 자바스크립트
1. 오태권
2. 오태권
3. 오태권
4. 오태권
5. 오태권
```

##### :pencil: 설명

- 이 풀이의 단점이 두개 있다.
- **단점 1. 유지보수가하기 어렵다.**
- **단점 2.중복 코드가 많다.**
- 이러한 문제를 함수의 활용을 통해서 유지보수하기 좋으면서 중복코드가 없는 코드를 구현할 수 있다.

<br>

##### :pencil: 풀이02) 함수를 활용할 경우

- 함수를 활용하여 좋은 점
  1) 코드 중복 제거 및 코드 재사용
  2) 유지보수 용이성

*​**:one: 코드 중복 제거 및 코드 재사용***

- **함수 사용 전**

```javascript
for(var i=1; i<=5; i++){
    document.write(i+". 프론트엔드<br>");
}
for(var i=1; i<=5; i++){
    document.write(i+". 자바스크립트<br>");
}
for(var i=1; i<=5; i++){
    document.write(i+". 오태권<br>");
}
```

<br>

- **함수 사용 후**

```javascript
// 함수 정의(재사용할 코드를 포장하는 기술)
function showName(name){
    for(var i=1; i<=5; i++){
        document.write(i+"."+name+"입니다. <br>");
    }
}
// 함수 호출 (함수 동작을 하게 하려면 함수 호출을 해야한다.)
showName("프론트엔드");
showName("자바스크립트");
showName("오태권");
```

<br>

*​**:two: 유지보수 용이성***

- 만약 출력 내용을 "프론트엔드"는 5번, "자바스크립트"는 10번 , "오태권"은 7번으로 변경해야 하는 경우 
- 반복문을 활용한 풀이에서는 **매개변수(파라미터 또는 인수)**를 이용하면 유지보수하기 좋은 코드를 만들 수 있다.

- **반복문 사용 풀이**

```javascript
for(var i=1; i<=5; i++){
    document.write(i+". 프론트엔드<br>");
}
for(var i=1; i<=10; i++){
    document.write(i+". 자바스크립트<br>");
}
for(var i=1; i<=7; i++){
    document.write(i+". 오태권<br>");
}
```

- **함수 사용 풀이**

```javascript
function showName(name, count){
    for(var i=1; i<=count; i++)
        document.write(i+"."+name+"입니다.<br>");
}
showName("프론트엔드", 5);
showName("자바스크립트", 10);
showName("오태권",7);
```

<br>

```
지금까지 함수를 활요앟면 중복 코드 제거 및 코드를 재사용할 수 있을 뿐 아니라 
유지보수하기 좋은 코드를 만들 수 있다. 
```

<br>

### _02. 함수란?_

- 함수는 특정 기능을 하는 구문(알고리즘, 로직)을 독립된 부품으로 만들어 재사용하고자 할 떄 사용하는 문법이다. 
  - 즉 일종의 포장방법

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/08.01_1.png?raw=true)

<br>

### _03. 함수 구조 3가지_

- 함수와 관련된 내용
  - 매개변수(파라미터 or 인수)
  - 변수
    - 지역변수
    - 전역변수
  - 리턴값
  - 함수 호출
  - 함수 정의
  - 함수 리터럴
  - 함수 이름 규칙

<br>

*​**:one: 첫 번째 : 일반적인 함수***

```javascript
function 함수이름(){
    실행구문;
}
```

<br>

*​**:two: 두 번째 : 매개변수가 있는 함수***

```javascript
function 함수이름([매개변수1[, 매개변수2[,....]]]){
    실행구문;
}
```

<br>

*​**:three: 세 번째 : 리턴값이 있는 함수***

```javascript
function 함수이름([매개변수1[, 매개변수2[,....]]]){
    실행구문;
    return 실행결과;
}
```

<br>

---

<br>

## :pencil:_Lesson 02. 가장 쉬운 함수 만들기_

### _01. 사용법_

##### :pencil: 문법

```javascript
function 함수이름(){
    실행구문;
    . . . .
}
```

##### :pencil: 설명

- 함수는 크게 함수 정의와 호출로 나눌 수 있다.
  - **함수 정의**는 일종의 설계도라 볼 수 있다. 설계만 한다고 해서 자동으로 동작하지는 않는다.
  - 함수 내부에 포장돼 있는 실행구문을 실행하고 싶을 때는 함수 호출을 해줘야한다.

<br>

**function**

- 변수를 만들 때 사용하는 `var`키워드와 마찬가지로 `function`은 함수를 만들 때 사용하는 키워드 이다. 

<br>

**함수이름**

- 함수이름은 변수 이름과 마찬가지로 유일해야 하며 만들려고 하는 함수의 기능을 함축하는 의미가 담긴 이름으로 만들어야 한다. 
- `{}`는 함수 영역을 나타낸다.

<br>

**함수이름()**

- 함수이름 + `()` 로 작성하면 함수가 동작한다. 
  - 이 작업을 함수 호출이라고 한다. == 전원버튼

<br>

### _02. 예제_

#### :memo:_예제 01)_ 다음 내용을 hello()라는 함수로 만들어 유지보수하기 쉽게 만들어라.

:ballot_box_with_check: **풀이전  코드 : 소스**

```javascript
document.write("안녕하세요. 환영합니다.", "<br>");
document.write("안녕하세요. 환영합니다.", "<br>");
document.write("안녕하세요. 환영합니다.", "<br>");
```

<br>

### 풀이

---

:one: **함수로 포장할 내용(중복코드 또는 로직) 찾기**

먼저 코드에서 함수로 포장할 만한 중복 코드나 재사용 로직이 있는지 확인한다.

```javascript
document.write("안녕하세요. 환영합니다.", "<br>");
document.write("안녕하세요. 환영합니다.", "<br>");
document.write("안녕하세요. 환영합니다.", "<br>");

// document.write("안녕하세요. 환영합니다.", "<br>"); 은 중복코드이다.
```

<br>

:two: **함수로 포장할 내용(중복코드 또는 로직) 찾기**

