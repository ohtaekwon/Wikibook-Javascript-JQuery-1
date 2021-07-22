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

이어서 중복 코드를 담을 함수를 만들어 준다.  함수를 만들어야 한다면 머릿속으로 바로! 함수 문법이 떠올라야 한다.

함수 본체를 만들기 위해 함수 문법을 다음과 같이 작성한다.

```javascript
function 함수이름(){
    실행구문;(포장할 내용을 여기에 작성한다.)
}
```

- 다음으로 함수 이름에 만들어야할 함수이름인 `hello`를 작성해야 한다.

```javascript
function hello(){
    실행구문;(포장할 내용을 여기에 작성)
}
```

<br>

:three: **중복코드 포장하기**

- 다음 함수에 중복코드를 포장한다.

```javascript
function hello(){
    document.write("안녕하세요. 환영합니다.","<br>");
}
```

<br>

:four: **중복코드 포장하기**

- 마지막으로 함수를 실행시키기 위해 함수호출을 한다.

```javascript
function hello(){
    document.write("안녕하세요. 환영합니다.","<br>");
}
hello();
hello();
hello();
```

<br>

#### :memo:_예제 02)_ 다음 내용을 printStar라는 함수로 만들어 간결하게 만들어라.

:ballot_box_with_check: **풀이전  코드 : 소스**

```javascript
var star="";
for(var i=1; i<=5; i++){
    for(var m=0; m<i; m++){
        star="*";
    }
    star+="<br>";
}
document.write(star);

var star="";
for(var i=1; i<=5; i++){
    for(var m=0; m<i; m++){
        star+="*";
    }
    star+="<br>";
}
document.write(star);
```

##### :computer: 실행결과

```
*
**
***
****
*****
*
**
***
****
*****
```

<br>

##### :pencil: 풀이

<br>

*​**:one: 단계 : 함수로 포장할 내용(중복코드 또는 로직)찾기***

- 코드를 확인하면 별표를 출력하는 로직이 중복해서 두 개 있는 것을 확인할 수 있다.

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/08.02_1.png?raw=true)

<br>*​**:two: 단계 : 빈 함수 만들기***

- 이어서 중복코드를 담을 `printStar()`라는 텅빈 함수를 만들어 준다.
  - 일종의 물건을 담을 빈 상자

```javascript
function printStar(){
    
}
```

<br>

*​**:three: 단계 : 중복 코드 포장하기***

- 중복코드를 `printStar()`함수에 포장한다.

```javascript
function printStar(){
    var star="";
    for(var i=1; i<=5; i++){
        for(var m=0; m<i; m++){
            star="*";
        }
        star+="<br>";
       
    }
    document.write(star);
}
```

<br>

*​**:four: 단계 : 함수호출***

- 마지막으로 함수를 두 번 호출해 준다.

```javascript
function printStar(){
    var star="";
    for(var i=1; i<=5; i++){
        for(var m=0; m<i; m++){
            star+="*";
        }
        star+="<br>";
    }
    document.write(star);
}
printStar();
printStar();
```

<br>

---

<br>

## :pencil:_Lesson 03. 지역변수 vs. 전역변수_

### _01. 변수 종류_

|             변수             | 설명                                                         |
| :--------------------------: | ------------------------------------------------------------ |
|         **전역변수**         | 전역에서 사용하는 데이터를 담는 변수이며 어디서든 접근해서 사용 가능하다.<br />(이제 막 스크립트를 시작한 초보자의 경우 가장 많이 사용) |
|         **지역변수**         | 특정 영역에서만 사용할 수 있는 변수<br />주로 함수 내부에 만들어지는 변수 |
| **매개변수<br />(파라미터)** | 함수 외부에서 함수 내부로 데이터를 전달하기 위한 용도로 사용하는 변수 |
| **멤버변수<br />(프로퍼티)** | 클래스 내부에서 만들어지며 주로 객체에서 사용하는 정보를 담는 변수 |

<br>

### _02. 지역변수와 전역변수 구분하기_

- 지역변수와 전역변수를 만드는 방법은 동일하다.
- 다른 점은 만드는 영역이 다르다는 것.
- 즉, 전역 영역에 변수를 만들면 == '전역변수'
- 지역 영역에 변수를 만들면 == '지역변수'

```html
<script>
    전역영역
    function func1(){
        지역 영역1
    }
    function func2(){
        지역 영역2
    }
</script>
```

<br>

#### :memo:_예제 01)_ 지역변수와 전역변수 구분하기

- 다음 예제를 실행하면 `1`, `2`, `3` , `4` , `5`에는 어떤 값이 출력될까

```html
<script>
    var name="test1";
    function func1(){
        var name="test2";
        document.write("2. name = "+ name, "<br>");	//--------(※2)
    }
    function func2(){
        var name="test3";
        document.write("3. name = "+ name, "<br>");	//--------(※3)
    }
    function func3(){
        name="test20";	//--------(※4)
        document.write("4. name = "+ name, "<br>");
    }
    document.write("1. name = "+ name, "<br>");	//--------(※1)
    func1();
    func2();
    func3();
    document.write("5. name = "+ name, "<br>");	//--------(※5)
</script>
```

```
1. name = test1
2. name = test2
3. name = test3
4. name = test20
5. name = test20
```

<br>

***전역 변수***

- 전역변수는 전역 영역에 만들어지는 변수로서 영역에 상관없이 사용할 수 있는 변수를 의미한다.
- 예제에서 전역 변수 name을 사용한 부분은 `(※1)`, `(※4)`, `(※5)`

<br>

***지역 변수***

- 지역변수는 지역 영역에 만들어지는 변수로서 **오직 만들어진 영역에서만 사용할 수 있다.**
- 예제에서 `(※2)`, `(※3)`는 전역변수 name과 지역변수 name을 사용할 수 있지만, 
- ***이름이 같은 경우 지역변수의 접근 순위가 높기 때문에 지역변수 name이 출력된다.***

<br>

### _03. 지역변수와 전역변수 생명주기_

- 여기서 생명주기란 만들어지고 없어지는 시기를 나타낸다.
- 지역변수와 전역변수는 이 생명주기가 다르다.

<br>

#### :memo:_예제 02)_ 지역변수와 전역변수 생명주기

```javascript
function func1(){
    var name="OHTAEKWON";
    document.write("1. name = "+name,"<br>");
}
func1();

// name은 지역변수이기 때문에 전역에서 사용할 수 없다.

document.write("2. name = " +name);
```

##### :computer: 실행결과

1. name = OHTAEKWON
2. name =

***전역 변수***

- 전역변수의 생명주기(변수를 사용할 수 있는 기간)는 자바스크립트가 실행되는 페이지가 브라우저에서 실행되고 있는 한 사라지지않고 계속 남아있는다. 
- 따라서, 어디서든 전역변수를 사용할 수 있다.

<br>

***지역 변수***

- 예제에서 `func1()`이라는 함수를 작성했다고 해서 함수 내부에 있는 지역변수 `name`이 자동으로 만들어지는 건 절대 아니다.
- 함수 내부는 오직 함수 호출을 해야 동작하며 자바스크립트 엔진에 의해 `var`라 해석되면서 지역변수가 만들어진다.
- 지역변수는 함수 내부의 구문실행이 모두 끝나는(`"}"`가 실행되는) 시점에 전역변수와는 달리 완전히 사라지게 된다.
- 따라서, ***지역변수는 전역변수와는 달리 변수가 만들어지는 지역에서만 사용할 수 있다.***

<br>

### _04. 예제_

#### :memo:_예제 03)_ 다음 예제를 실행하면 1,2,3,4에는 어떤 값이 출력될까?

```javascript
var a = 10;
var b = 100;
function func1(){
    var b = 20;
    document.write("1. a = " +a+ "<br>");	//----------(※1)
    document.write("2. b = " +b+ "<br>");	//----------(※2)
    a = 50;	//----------(※3)
}
func1();

document.write("3. a = " +a+ "<br>");	//----------(※4)
document.write("4. b = " +b+ "<br>");	//----------(※5)
```

```
1. a = 10
2. b = 20
3. a = 50
4. b = 100
```

##### :pencil: 설명

- `(※1)`에서는 전역변수 a의 값이 10이 출력
- `(※2)`에서는 지역변수 b의 값이 20이 출력된다.
- `(※4)`에서는 `(※3)`에서 전역변수 a의 값이 10에서 50으로 변경 되었기 때문에 50이 출력
- `(※5)`에서는 전역변수 b의 값 100이 출력된다.

<br>

---

<br>

## :pencil:_Lesson 04. 매개변수가 있는 함수 만들기_

- **매개변수란?**
  - 함수 외부에서 함수 내부로 데이터를 전달할 때 사용하는 변수

<br>

### _01. 사용법_

##### :pencil: 문법

```javascript
function 함수이름([매개변수1, 매개변수2, . . . .]){
    실행구문;
}
```

<br>

##### :pencil: 설명

- 문법은 매개변수가 있는 것을 제외하면 기본 함수와 동일하다.
- 매개변수를 총 6개의 주제로 나누면
  1. **매개변수의 사용**
  2. **매개변수란?**
  3. **매개변수 위치**
  4. **매개변수는 지역변수**
  5. **매개변수 개수**
  6. **매개변수에 데이터 전달하기**

<br>

*​**:one: 매개변수는 이럴 때 사용한다.***

- **출력결과**
  - 프론트엔드님 환영합니다.
  - 자바스크립트님 환영합니다.
  - 오태권님 환영합니다.

```javascript
function hello(){
    var name="프론트엔드";
    document.write(name+"님 환영합니다. ");
}
hello();
```

- 이렇게 한다면, "프론트엔드님 환영합니다." 까지는 처리할 수 있지만, 자바스크립트, 오태권의 메시지를 출력은 할 수 가 없다.
- 하지만, 문제는 name이 함수 내부에 `지역변수`로 되어 있어 함수가 한 번 실행되면 함수 외부에서 함수 내부를 접근할 수 없게 되어 처리할 수가 없다.

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/08.03_1.png?raw=true)

- 지금까지 배운 방법으로는 이 문제를 해결할 수 없다.
- 하지만, 먼저 실행전에 hello()함수에 구멍(매개변수)를 뚫어 놓는다.
- 구멍에는 한 개부터 수백 개까지 만들고 싶은 만큼 만들 수 있다.
- 또한, 구멍마다 이름을 붙일 수 가 있는데,
  - 이 이름을 만드는 규칙은 변수이름 만드는 방법과 동일하다

![08.03_2.png](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/08.03_2.png?raw=true)

- 이제 함수를 호출 할 때 이 구멍을 통해 함수 외부에서 함수 내부로 데이터를 전달한다.

```javascript
function hello(value){
    var name = value;
    document.write(name+"님 환영합니다.");
}

/*
	함수를 호출하면 값이 매개변수인 value로 넘어간다.
	즉, value = "프론트엔드"와 같게 된다.
*/
hello("프론트엔드"); 
hello("자바스크립트");
hello("오태권");

// 이제 함수를 호출 할 때마다 value라는 구멍에 값을 넘겨 함수 내부에 있는 변수 name의 값을 변경할 수 있다.
```

<br>

*​**:two: 매개변수란?***

- 매개변수는 변수의 일종이며 함수 외부에서 함수 내부로 데이터를 전달할 때 매개체 역할을 하는 변수이다. 
- 즉, 함수 외부에서 함수 내부로 데이터를 전달할 때 사용하는 변수

```javascript
// 함수A("data");
// "data"가 paraml으로 전달된다.


function 함수A(paraml){
    //이곳은 함수 내부
    document.write(param1);
}
```

<br>

*​**:three: 매개변수 위치***

- 매개변수 위치는 함수 이름 안에 위치한다.

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/08.03_3.png?raw=true)

<br>

*​**:four: 매개변수는 지역변수***

- 또한 매개변수는 지역변수이기도 한다.
- 이는 ***함수가 실행될 때 만들어지고 함수가 종료되면 자동으로 사라진다.***
- 지역변수가 매개변수와 다른 점은 매개변수를 만들 때 var를 붙이지 않는다.

```html
<script>
    function 함수A(paraml){
        . . .. 
        alert("paraml ="+ paraml) // paraml(o) : 매개변수는 함수A() 내부에서만 사용이 가능하다.
    }
    
    함수A("datal");
    alert("paraml ="+ paraml);	// prarml(x) : 매개변수는 지역변수와 동일하기 때문에 함수 외부에서는 사용할 수 가 없다.

</script>
```

<br>

*​**:five: 매개변수 개수***

- 매개변수 개수 역시 일반 변수처럼 열 개든 스무 개든 만들고 싶은 만큼 만들 수 있다/
- 매개변수를 하나를 추가해 '방문 횟수'를 나타낼 수 있다.

```javascript
function hello(name, count){
    document.write(name+"님 "+count+"번째 방문을 환영합니다.");
}
hello("오태권", 20);
```

<br>

*​**:six: 매개변수에 데이터 전달하기***

- 함수 매개변수에 데이터를 전달하는 방법은 함수를 호출할 때 데이터를 넣어 호출해 준다.
- 만약 매개변수가 두 개면 함수 호출 시 데이터를 두개 넣어준다. 

```javascript
function hello(name, count){
    document.write(name + "님 " + count+"번째 방문을 환영합니다.");
}
hello("오태권",200);
```

- `hello()`를 실행하면 `"오태권"` 데이터는 name에, `200`은 count에 저장된다.
  - 이는 일반 변수를 만들며면서 데이터 초기화시키는 것과 같다. 
  - name = "오태권"
  - count = 200;

<br>

- 매개변수가 두 개인데, 하나만 보낸 경우

```javascript
function hello(name, count){
    document.write(name + "님 " + count+"번째 방문을 환영합니다.");
}
hello("오태권");
```

```
오태권님 undefined번째 방문을 환영합니다.
```

- count에는 undefined가 저장된다.

<br>

### _02. 예제_

#### :memo:_예제 01)_ 매개변수로 받은 두 수를 더한 결과값을 출력하는 함수를 만들어라.

```javascript
function sum(num1, num2){
    var result = num1 + num2;
    alert("두수의 합은 = " + result);
}
sum(10,20);
```

````
두수의 합은 = 30
````

##### :pencil: 설명

- 먼저 합한다는 의미를 가진 sum을 만든 후 외부에서 데이터를 받기 위해 매개변수를 두 개 만든다.
- 그리고, 함수 내부에 이 두 매개변수 값을 더한 결과값을 출력하는 구문을 작성한다.
- 마지막으로 숫자 10과 20을 매개변수 값으로 해서 sum()함수를 호출한다.

<br>

***이런 식으로 함수에 매개변수를 만들어 함수 호출 시 외부에서 데이터를 받아 함수 내부에서 사용하면 된다.***

<br>

### _03. arguments란?_

#### :memo:_예제 02)_ 다음 코드가 실행되면 어떤 값이 출력될까?

```javascript
function showInfo(){
    alert("안녕하세요. "+userName+"님의 나이는 "+age+"입니다. ");
}
showInfo("오태권",30);
```

##### :computer: 실행결과

- Uncaught ReferenceError: userName is not defined

##### :pencil: 설명

- 함수 호출 시 값을 넘겼지만 값을 받는 매개변수가 선언돼 있지 않기 때문에 아무런 값이 찍히지 않는다.
- 자바스크립트는 userNmae을 발견하면 우선 지역변수와 매개변수 중에서 userName을 찾난다.
- 만약 발견하지 않는다면 지역변수에서 찾아 사용한다.
- 전역변수에도 없다면 userName이란 변수가 없는 것으로 판단하고 에러를 발생시킨다.

<br>

***매개변수를 선언하지 않고 매개변수 값에 접근하는 방법으로 자바스크립트 함수는 argument라는 객체를 기본으로 제공한다.***

- argument에는 모든 매개변수 값이 들어있다.

<br>

- ***arguement란?***
  - 매개변수의 모든 정보가 담겨있는 장소(객체)
  - 배열은 아니지만 배열처럼 사용하면 된다.
  - 매개변수의 개수는 argument의 length 프로퍼티를 이용하면 알 수 있다.

```javascript
function showInfo(){
    console.log("0 = "+arguments[0]);
    console.log("1 = "+arguments[1]);
    alert("안녕하세요. "+arguments[0]+"님의 나이는 "+arguments[1]+"입니다."); 
}
showInfo("오태권",30);
```

<br>

---

<br>

## :pencil:_Lesson 05. 리턴값이 있는 함수 만들기_

### _01. 사용법_

##### :pencil: 문법

```javascript
function 함수이름([매개변수1, 매개변수2,. . . . ]){
    실행구문;
    
    [return 리턴값;]
}
```

:computer: **호출**

- var 변수 = 함수이름();

##### :pencil: 설명

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/08.05_1.png?raw=true)

- 문법은 리턴값이 있는 것을 제외하면 매개변수가 있는 함수와 동일

<br>

:diamond_shape_with_a_dot_inside: **리턴값(return)이란?**

함수 내부는 함수라는 철벽으로 포장돼 있기 때문에 한번 실행되면 함수 외부에서 접근할 수 없다고 했다.

이때 매개변수를 활용하면 함수 내부로 데이터를 전달할 수 있다.

- **리턴값**은 매개변수와 반대되는 값
  - 매개변수 값이 함수 외부에서 함수 내부로 들어오는 입력값이라면,
  - 리턴 값은 ***함수 내부에서 처리한 결과값을 함수 외부로 전달하기 위해 사용하는 일종의 출력값***이다.
  - 이때 사용하는 구문이 바로 `return` 명령어 

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/08.05_3.png?raw=true)

<br>

### _02. 예제_

#### :memo:_예제 01)_ 두 수를 매개변수로 받은 후 이 두 값을 더한 결과값을 리턴하는 함수sum()을 만들어라

```javascript
function sum(num1, num2){
    var result = num1+num2;
    return result;
}

var value=sum(10,30);
alert("두 수의 합은 = " + value);
```

##### :pencil: 설명

- return문을 이용해서 함수 내부에서 처리한 결과값을 함수 외부로 전달했다.
- 즉, 다음 내용이 실행되면
  - var value = sum(10,30);
- 쉽게 알수 있는 구문처럼 함수 내부에서 리턴한 값 40이 value변수에 대입된다고 생각해보자.

| 실행 전                 | 실행 후         |
| ----------------------- | --------------- |
| var value = sum(10,20); | var value = 40; |

<br>

:question: **질문** :question: 

- 리턴값이 있는 경우는 항상 변수로 받아야 하는것인가?
  - 아니다
  - 필요 없다면 리턴값을 굳이 변수에 저장하지 않아도 된다. 

<br>

### _03. return문의 또 다른 용도_

- return문은 **함수 내부의 데이터를 → 함수를 호출한 곳으로 전달할 때**도 사용하지만 **함수를 즉시 빠져 나오는 기능**도 한다.
- **함수내부 데이터를 외부로 호출**
- **함수를 즉시 빠져 나오는 기능**

<br>

#### :memo:_예제 02)_ 무한 루프를 돌며 숫자를 입력받고 입력받은 수익 합을 화면에 출력하는 기능을 sample()이라는 함수에 만들어 보시오. (단, 입력값이 0이면 즉시 실행을 멈춰라)

```javascript
function sample(){
    var sum=0;
    var count=1;
    
    // 무한루프 시작
    while(true){
        var value=parseInt(window.prompt("수 입력",1));
        if(value==0){
            document.write("종료합니다.");
            
            // 함수 탈출
            return; //------------(※1)
        }
        
        // 입력값 더하기
        sum+=value;
        // 입력값 출력하기
        document.write(count+". "+sum+"<br>");
        count++
    }
    //------------(※2)
    document.write("총 "+count+"번 실행했습니다.");
}
// 함수 호출
sample();
```

##### :pencil: 설명

- 앞에서 설명한 것처럼 **return**의 또 다른 기능은 ***함수를 멈추고 즉시 탈출할 수 있는 기능***을 가지고 있다.
- 언뜻 보면 **break**와 비슷해 보일 수도 있지만 완전히 다른 동작을 한다.
- 만약 예제에서 `※1`의 return문을 **break문으로 변경해 실행하는 경우 자바스크립트는 while() 루프를 빠져 나온후** `※2`구문을 실행하게 된다.
- 이와 달리 return문은 실행 즉시 함수를 탈출하기 떄문에 총 반복 횟수를 출력하는 구문을 실행하지 않게 된다.
- ***정리하자면 break문은 루프 탈출 기능이고, return문은 함수 탈출이다.***

<br>

---

<br>

## :pencil:_Lesson 06. 함수 이름 만들 때 주의사항_

- 변수 이름과 마찬가지로 함수 이름 역시 지켜야할 규칙이 있다.

<br>

*​**:one: 숫자로 시작하면 안된다.***

```javascript
function 1st(){
    
} 
// 숫자로 시작하는 것은 불가능하다.
```

<br>

*​**:two: 대소문자 구분: ex) name과 Name은 완전히 다른 함수이다.***

```javascript
// 일반 함수
function showUserName(){
    
}
// 일반 클래스
function ShowUserName(){
    
}
```

- 함수 이름이 모두 같더라도 대소문자가 다르면 완전히 다른 함수로 해석한다.
- 일반함수의 경우 : 소문자로 시작하며 클래스를 만들 땐 대문자로 함수를 만든다.
- 함수가 대문자로 되어 있으면 일반 함수가 아닌 클래스로 판단해 다음 처럼 호출 방법이 완전히 달라지게 된다.

```javascript
// "소문자로 시작하니 일반 함수군,호출해서 사용하면 되겠군."

showUserName();

// "대문자로 시작하니 클래스군. 객체의 인스턴스를 생성해서 사용하면 되겠군."
var user = new ShowUserName();
```

<br>

*​**:three: 낙타표기법(camelcase): 여러 단어가 조합되는 경우 소문자와 대문자를 번갈아 넣어 표기***

```javascript
function showUserName(){
    
}
```

<br>

---



