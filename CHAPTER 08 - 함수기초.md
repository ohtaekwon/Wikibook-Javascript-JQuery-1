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

