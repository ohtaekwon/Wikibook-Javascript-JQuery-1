# _CHAPTER 01_ - 변수

<br>

## :speaker: INTRO

<br>

:pushpin:***변수란?***

- 데이터를 보관하는 장소
- 필요할 때 언제든지 사용할 수 있다.

```javascript
var 변수이름 = 저장데이터; // 변수를 만드는 문법
```

<br>

***EX1) 변수의 유형***

|          변수          | 설명                                                         | 다루는 장        |
| :--------------------: | ------------------------------------------------------------ | ---------------- |
|      **전역변수**      | ***전역에서 사용하는 데이터를 담는 변수이며 어디서든 접근해서 사용이 가능하다.*** | 01부             |
|      **지역변수**      | ***특정 영역에서만 사용할 수 있는 변수<br />주로 함수 내부에 만들어지는 변수이다.*** | 02부 01장 함수   |
| **매개변수(파라미터)** | ***함수 외부에서 함수 내부로 데이터를 전달하기 위한 용도로 사용하는 변수*** | 02부 01장 함수   |
| **멤버변수(프로퍼티)** | ***클래스 내부에 만들어지며 주로 객체에서 사용하는 정보를 담는 변수*** | 05부 01장 클래스 |

<br>

|     Lesson      |                   Content                    |
| :-------------: | :------------------------------------------: |
| ***Lesson 01*** |                **변수 소개**                 |
| ***Lesson 02*** |               **변수 만들기**                |
| ***Lesson 03*** |    **변수에 저장할 수 있는 데이터 종류**     |
| ***Lesson 04*** |           **변숫값 저장 및 변경**            |
| ***Lesson 05*** |     **변숫값이 자동으로 읽혀지는 경우**      |
| ***Lesson 06*** | **변수를 활용한 데이터 중복 제거 및 재사용** |
| ***Lesson 07*** |  **변수에 어떤 값이 들어 있는지 확인하기**   |
| ***Lesson 08*** |                   **주석**                   |
| ***Lesson 09*** |                   **배열**                   |
| ***Lesson 10*** |                **변수 종류**                 |
| ***Lesson 11*** |                   **미션**                   |

<br>

<br>

## :pencil:_Lesson 01. 변수소개_

### _01. 변수란?_

- 물건을 보관했다가 필요할 떄 다시 꺼내 사용하는 일종의 **`창고`**역할을 한다.
- `창고`와 **`변수`**의 차이점이라면 보관하는 내용이 ***`데이터`*** 라는 점
  - 변수는 데이터를 저장하는 장소
  - 변수는 데이터를 일고 쓰고 할수 있는 장소

![](https://user-images.githubusercontent.com/75871005/125393160-631ea980-e3e2-11eb-9479-bb58a6b16655.png)　

<br>

### _02. 변수는 이럴 때 사용한다._

- 특정 사이트의 **로그인 상태 유무**를 변수에 저장한다.
- 사용자가 선택한 **메뉴 항목**도 변수에 저장한다.
- 사이트에 멋지게 출력돼 있는 메뉴 항목 역시 처음엔 배열 변수에 저장된 내용
- 슈팅 게임에서 현재 기록 중인 점수도 변수에 저장한다.
- 슈팅 게임에서 현재 남아있는 캐릭터의 에너지 역시 변수에 저장된다.
- 쇼핑몰 **장바구니**에 담겨 있는 **상품목록**들 변수에 저장
- 화면 가득 출력된 게시물 목록도 배열 젼수에 저장돼 있는 내용을 출력한 것.

<br>

---

<br>

## :pencil:_Lesson 02. 변수 만들기_

### _01. 변수 하나 만들기_

```javascript
var 변수이름 = 값;  
// "자바스크립트 엔진에게 변수를 하나 만든 후 여기에 값을 저장해주세요"
// 자바스크립트에서 변수를 만드는 가장 일반적인 방법
```

- **var의 정체**
  - var는 변수 선언을 의미하는 키워드이다.
  - 자바스크립트 엔진은 소스를 해석하는 도중 var라는 키워드를 만나면 **`"여기는 변수를 만들라는 말"`**으로 해석한다.
    - **`키워드(Keyword)`**란 이미 특정한 목적으로 만들어져 있는 자바스크립트 요소 ex. **`if`**, **`for`** 등
- **;(세미콜론)의 의미**
  - 문장 맨 뒤에 붙이는 세미콜론은 **문장의 끝**을 의미한다.
  - 자바스크립트 엔진은 소스를 해석하는 도중 세미콜론을 만나면 **`"여기서 하나의 문장(구문)이 끝나는 곳"`**으로 해석하여 다음 줄로 이동해 다른 코드를 해석한다.

```
변수는 "=" 연산자를 기준으로 var에 의해서 "변수이름"으로 변수가 만들어지고, 
이후 우측에 있는 데이터가 변수에 저장(대입)된다.
```

![](https://user-images.githubusercontent.com/75871005/125412680-1777fa00-e3fa-11eb-986e-c2487f18b85b.png)

<br>

#### :memo:_예제 01)_ 여러분의 나이가 담긴 변수 age를 만들어 주세요

```html
<!DOCTYPE HTML>
<html>
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	<title> </title>

	<script>
        /*
         예제01: 여러분의 나이가 담긴 변수 age를 만들어 주세요.

        */
		var age = 30;

	</script>
</head>

<body>

	</body>
</html>

```

<br>

### _02. 변수 여러 개 만들기_

> **방법 01)**  ***var를 이용해서 여러 줄로 변수를 구분하는 경우***

```javascript
var 변수이름1 = 데이터;
var 변수이름2 = 데이터;

....
```

<br>

#### :memo:_예제 02)_ 여러분의 이름과 나이를 저장한 변수를 만들어주세요

```javascript
var age = 30;
var name = "TK";
```

<br>

> **방법 02)**  ***콤마(,)를 이용해서 변수 구분을 하는 경우***

```javascript
var 변수이름1 = 데이터[, 변수이름2 = 데이터...];
```

- `[]`의 의미는 내부에 들어있는 내용을 생략해도 된다는 의미이다.

  - `변수이름 = 값`을 하나 이상 작성할 수도 있다는 의미

    <br>

#### :memo:_예제 03)_ 여러분의 이름과 나이를 저장한 변수를 콤마(,)를 이용해서 만들어주세요

```javascript
var name= "TK", age = 30;
```

<br>

### _03. 변수이름 만들 때 주의사항_

> **01)**  ***숫자로 시작하면 안 된 다.***

```javascript
var 1st = 10; //에러
```

- 숫자로 시작하는 변수를 만들면 에러가 발생하여 브라우저가 자바스크립트를 실행할 수 없다.

<br>

> **02)**  ***대소문자 구분:  name과 Name은 완전히 다른 변수.***

```javascript
var name = "TK";
var Name = "TK";
```

- **자바스크립트는 변수 이름이 모두 같더라도 대소문자가 다르면 완전히 다른 변수로 해석한다.**
  - 두 개의 창고가 만들어지는 셈

![](https://user-images.githubusercontent.com/75871005/125416008-ec52ea55-a883-4d8d-8009-e8d99bb0eacb.png)

<br>

> **03)**  ***변수는 대문자가 아닌 소문자로 시작해라***

```javascript
var Name = "TK";
// 대신
var name = "TK";
// 가 더 권장
```

- JAVA, C#과 같은 일반 언어 역시 변수 이름은 대부분 **소문자**로 시작

<br>

> **04)**  ***변하지 않는 환경 변수의 값을 담는 상수 변수는 모두 대문자로 만들어라***

```javascript
var DB_NAME = "webdonne";
var ADMIN_ID = "ddandongne";
```

- DB 이름이나 관리자(ADMIN) 이름같은 경우 한 번 저장한 후 **`변경하면 안되는 값`**들이 있다.
- 이런 상수 값을 담는 변수는 다른 변수와 구분이 될 수 있게 변수 이름을 모두 **대문자**로 만든다.

<br>

즉, 대문자로 된 변수를 만나게 되면 앞으로는 ***"값을 변경하면 안 되는 변수로군, 그냥 사용하기만 하라는 의미군"***이라고 생각해준다.

<br>

> **05)**  ***여러 단어가 조합되는 경우 다음과 같이 낙타 표기법(camelcase)로 작성해주어야한다.***

```javascript
var userName = "OHTAEKWON";
var selectMenuIndex = 1;
```

- 이 표기법 역시 관행일 뿐 반드시는 아님.
- userName을 username or user_name으로 만들어도 된다.

<br>

> **06)**  ***자바스크립트에서 이미 정의된 예약어(키워드)를 사용하면 안 된다.***

***예약어 목록***

```
braek, case, catch, continue, defalut, delelte, do, else, finally, for, function, if, in,
instanceof, new, return, switch, this, throw, try, typeof, var, void, while, with
```

<br>

```javascript
// 6. 자바스크립트에서 이미 정의된 예약어(키워드)를 사용하면 안돼요.
var class = "test1";		// 에러
var for = "test2";			// 에러
var if = "test3";			// 에러
```

<br>

---

<br>

## :pencil:_Lesson 03. 변수에 저장할 수 있는 데이터 종류_

- 변수에는 숫자와 문자뿐만 아니라 **함수**와 **클래스** 까지 저장할 수 있다.

<br>

### _01. 데이터 위치_

- 일반적으로 **`변수(저장소)`**는 `"="`를 기준으로 **좌측**에 오고 데이터는 **우측**에 온다.

![](https://user-images.githubusercontent.com/75871005/125412680-1777fa00-e3fa-11eb-986e-c2487f18b85b.png)

<br>

### _02. 데이터 종류_

- 변수에 저장할 수 있는 데이터 종류는 총 8개 정도 된다.
  - 숫자(Number)
  - 논리(Boolean)
  - 문자(String)
  - 함수(Function)
  - 클래스(Calss)
  - 클래스 인스턴스(Class Instance)
  - undefined
  - null

![](https://user-images.githubusercontent.com/75871005/125419614-b8f3345e-6a29-4f73-81cc-6f81ad42c5aa.png)

- **데이터형이란?** 
  - 변수에 저장(보관)할 수 있는 값을 의미한다.

| 데이터형          | 범위                                                         | 예                                                         |
| ----------------- | ------------------------------------------------------------ | ---------------------------------------------------------- |
| 숫자형(Number)    | +-5.0x10-324+-1.7x10308                                      | var age = 30;<br />var weight=60.25;                       |
| 문자형(String)    | "문자열"                                                     | var name="TK";                                             |
| 논리형(Boolean)   | true(참), false(거짓)                                        | var isLogin=false;                                         |
| 특수형(undefined) | 변수는 선언했지만 값이 아직 할당되지 않은 상태               | varUsername; //기본값 undefined                            |
| 특수값(null)      | 값이 아직 없다는 의미, 일반적으로 undefined와 같은 의미로 사용 | var myClass=null;                                          |
| 함수(Function)    |                                                              | function showMenu(){<br />}<br />var func = showMenu;      |
| 클래스(Calss)     |                                                              | function MyClass(){<br />}<br />var myClass = MyClass;     |
| 객체(Object)      |                                                              | function MyClass(){<br />}<br />var myClass = new MyClass; |

<br>

:page_facing_up: 의미파악

> **1) 숫자형(Number)**

- 숫자형은 일상 생활에서 사용하는 일반적인 숫자
- 크게 `정수형` 과 `실수형`으로 나눠진다.
  - 10진수와 실수형은 일반적으로 사용하는 숫자
  - 16진수는 글자색이나 배경색을 나타낼 때 주로 사용

| 자료형        | 내용                                                         | 예                                                   |
| ------------- | ------------------------------------------------------------ | ---------------------------------------------------- |
| 정수형 10진수 | 일상 생활에서 사용하는 숫자이며 소수점이 없음                | var age = 30;                                        |
| 정수형 16진수 | 0x로 시작하며 숫자 0~9와 문자 A~F를 사용해서 모든 숫자를 표현함.<br />***주로 색상 값을 나타낼 때 사용한다.*** | var color = 0xF00; //빨간색<br />var color = "#f00"; |
| 실수형        | 소수점을 갖는 숫자                                           | var weight = 69.8; //몸무게                          |

- 숫자형 변수는 실무에서 다음과 같이 사용된다.
  - 나이, 몸무게와 같은 숫자 정보를 저장할 때 숫자형을 사용
  - 슈팅게임에서 현재 기록중인 게임 점수를 저장할 때 숫자형 변수를 사용
  - 슈팅게임에서 현재 남아있는 에너지를 저장할 때 숫자형 변수를 사용
  - 홈페이지 메뉴에서 현재 선택된 메뉴 인덱스 값을 저장할 때 숫자형을 사용

<br>

#### :memo:_예제 01)_ 여러분의 나이 몸무게를 각각 age, weight 변수에 담아 주세요

```javascript
var age = 30;
var weight = 69.8;
```

<br>

> **2) 문자형(String)**

```javascript
var userName = "프론트엔드";
```

- ***문자열이란?*** 일상생활에서 사용하는 글자를 프로그래밍 동네에서는 문자열이라고 부를 뿐 다른 차이는 없다.
- 문자형 변수는 실무에서 다음과 같이 사용된다.
  - 홈페이지의 메뉴 항목과 같은 글자 정보를 저장할 때 문자형 변수를 사용
  - 홈페이지에 로그인할 때 사용하는 아이디와 패스워드도 문자형 변수에 담아 사용
  - 게시판의 게시물 제목, 날짜, 글쓴이 본문 등 모두 문자형 변수에 담아 사용
  - 이름, 닉네임, 주소, 정보를 담을 떄 문자형 변수를 사용

#### :memo:_예제 02)_ 여러분의 아이디를 id라는 변수에 저장해 주세요

```javascript
var id = "TKOH";
```

<br>

#### :memo:_예제 03)_ 여러분의 나이를 age라는 변수에 문자열 값으로 저장해주세요

```javascript
var age = "30";
```

<br>

#### :exclamation: ​참고 하기 :exclamation:

```
1. var age = 30과 
2. var age = "30"은 서로 다르다.

1.은 숫자형 30을 의미하며 2는 문자열 30을 의미한다.
```

<br>

> **3) 논리형(Boolean)**

```javascript
var login=true;
```

- 논리형은 오직 `참(true,1)`과 `거짓(false,0) 두 가지 값이 존재한다. 

<br>

#### :memo:_예제 04)_ 현재 날씨가 추운지 아닌지 cold 변수에 담아 표현해 주세요

```javascript
var cold = false;
```

<br>

#### :memo:_예제 05)_ 로그인 유무를 login 변수에 담아보세요 

```javascript
var login = true;
```

<br>

> **4) undefined**

- 변수에 undefined가 저장되어 있다면 이것은 일반적으로 변수 만든 후 초기화하지 않은 상태를 의미한다.

#### :memo:_예제 06)_ 변수를 선언하고 그 변수에 값을 대입하지 않는 경우 

```javascript
var data1;
alert("data1 = " + data1);

// 실행결과
// data1 = undefined
```

- 설명
  - **변수를 선언한 후 아무런 값을 넣지 않은 경우 변수**에는 **undefined**라는 값이 기본적으로 저장된다.
  - alert()은 알림창을 출력해주는 기능으로 변수에 들어 있는 내용을 확인할 수 있다.

<br>

#### :memo:_예제 07)_ 함수 인자 값 없이 함수를 호출하는 경우

```javascript
function myFunc(data1){
    alert("data1= " + data1);
}
myFunc("value1"); //------※1
myFunc(); //------※2

// 실행결과
// data1 = value1 
// data1 = undefined
```

- `※1`의 경우 data1="value1"를 넣은 것과 일치한다.
- `※2`의 경우 data1=undefined를 넣은 것과 일치한다.

***즉, 매개변수(인자)가 있는 함수를 인자 값 없이 호출하는 경우에도 해당 매개변수에 undefined가 저장된다.***

<br>

#### :memo:_예제 08)_ 존재하지 않는 객체의 프로퍼티에 접근하는 경우

```javascript
function MyClass(){
    this.name="TK";
}
var test1 = new MyClass();
alert("test1.name= " + test1.name);
alert("test1.userName= " + test1.Name);


// 실행결과
// test1.name = TK
// test1.userName = undefined
```

- test1.name은 객체의 프로퍼티로서 일종의 변수라고 생각하면 된다.
- test1.name 대신 test1.userName과 같이 객체에 존재하지 않는 변수를 접근하는 경우에도 undefined가 출력된다.

***즉, 변수를 선언하고 값을 아무것도 넣지 않으면 undefined이 기본값으로 들어간다!***라고 정리하면 된다.

<br>

> **5) null**

- null의 뜻은 ***"아무것도 참조하고 있지 않다."***라는 의미가 담겨 있다.
- 주로 객체를 담을 변수를 초기화할 때 많이 사용한다.

<br>

#### :memo:_예제 09)_ null 값으로 데이터를 초기화하는 경우

```javascript
// 숫자 변수 초기화
var data1 = 0;

// 문자 변수 초기화
var data2 = "";

// 논리형 변수 초기화
var data3 = false;

// 객체 변수 초기화
var data4 = null;
```

- 설명
  - 일반적으로 초기화와 동시에 변수를 만들게 되는데 이때 초깃밧을 보면 앞으로 이 변수가 어떤 데이터형을 저장할 변수인지 알 수 있다.
    - ex) data3 = false의 경우 초깃값을 보면 이 변수에는 true 또는 false가 저장되는 boolean변수인 것을 알 수 있다.

<br>

#### :exclamation: ​참고 하기 :exclamation:

```
- undefined는 변수의 기본 초깃값이며
- null은 객체를 담을 변수를 초기화할 떄 사용하는 값이다.
```

<br>

----

<br>

## :pencil:_Lesson 04. 변숫값 저장 및 변경_

### _01. 변숫값 저장_

- 변수에는 상수뿐 아니라 또 다른 변수 자체를 저장할 수 있다.

```javascript
var 변수A = 데이터; //------※1
var 변수B = 변수A; //------※2
var 변수C = 변수 A + 데이터 + 변수B; //------※3
```

- `※1`은 데이터가 변수A에 저장된다.
- `※2`는 변수B에 변수A가 저장되는 것은 아니라 변수B에 ***`변수A에 들어있는 값이 복사돼 저장된다.`***

![01.04_1](https://user-images.githubusercontent.com/75871005/125442733-d484f993-3c4e-4d5b-b7b1-df96ba9bfe8a.png)

- 정리하면 자바스크린트 엔진은 다음과 같이 해석해 처리한다.

***해석 전***

```javascript
var data1 = 10;
var data2 = data1;
var data3 = data1 + 20 + data2;
```

<br>

***해석 후***

```javascript
var data1 = 10;
var data2 = 10;
var data3 = 10 + 20 + 10;
```

<br>

#### :memo:_예제 01)_ 변수 data1를 만든 후 숫자 데이터 1234를 저장해주세요 그리고 변수 data2를 만든 후 data1의 값을 저장해 주세요

```javascript
var data1 = 1234;	// 1234
var data2 = data1;	// 1234
```

<br>

### _02. 변숫값 변경_

```javascript
var 변수이름 = 데이터;
변수이름 = 신규 데이터1;
변수이름 = 신규 데이터2;
```

- 변수에 저장되어 있는 값을 다른 값으로 변경하는 방법
  - **var를 붙이지 않은 상태**에서 변수에 값을 대입하면 된다.

<br>

#### :memo:_예제 02)_ 변수 data1을 만든 다음 초깃값을 10으로 한 후 데이터를 다시 20으로 또 다시 한 번 30으로 변경해주세요.

```javascript
var data1 = 10;		// 10
data1 = 20;			// 20
data1 = 30;			// 30
```

<br>

#### :exclamation: ​돌발 질문 :exclamation:

```javascript
// 다음 1 과 2의 차이점은 무엇인가?

//-------※1.
var data1 = 10;
var data2 = 20;
var data3 = 30;

//-------※2.
var data1 = 10;
data1 = 20;
data2 = 30;
```

- `※1`과 `※2` 모두 data1에 최정적으로 `30`이라는 값이 저장된다는 것은 같다.
- 하지만, `※1`의 경우 data1이라는 똑같은 저장공간이 세 번 만들어지는 것이고,
- `※2`의 경우 data1이라는 저장공간은 딱 한번 만들어진다는 것이 다르다.
- ***실무에서 `※1`처럼 작성하는 일은 없어야한다.***

<br>

---

<br>

## :pencil:_Lesson 05. 변숫값이 자동으로 읽혀지는 경우_

변수는 다음과 같은 경우에 값이 자동으로 읽혀진다.

1. 우측에 변수를 두는 경우
2. 함수 호출 시 변수를 매개변수(파라미터) 값으로 사용하는 경우
3. 연산자와 함께 사용하는 경우

<br>

### _01. 우측에 변수를 두는 경우_ (변수에 들어있는 값이 읽혀 다른 변수에 대입하는 경우)

```javascript
변수A = 변수B(우측에 있을 때)
```

<br>

#### :memo:_예제 01)_ 다음 구문이 어떻게 해석되는지 설명해주세요

```javascript
var name = "OHTAEKWON";
var temp = name;

name // OHTAEKWON
tmep // OHTAEKWON
```

- 설명
  - `name` 변수에 들어 있는 값이 복사돼 `temp` 변수에 대입된다.

<br>

### _02. 함수 호출 시 변수를 매개변수 값으로 사용하는 경우_

```
함수(변수A);
```

<br>

#### :memo:_예제 02)_ 다음 구문이 어떻게 해석되는지 설명하시오

```javascript
function teat1(userName){
    alert("userName =" +userName);
}
var name = "OHTAEKWON";
test1(name);
```

- 설명
  - test1(name); 을 호출하면 test1("OHTAEKWON")로 변경된다.

<br>

### _03. 연산자와 함께 사용하는 경우_

```
변수A = 변수B 연산자 변수C;
```

<br>

#### :memo:_예제 03)_ 다음 구문이 어떻게 해석되는지 설명해주세요

```javascript
var num1 = 10;
var num2 = 20;
var result = num1 + num2;
alert(result);
```

- var result = num1 + num2를 호출하면, var result = 10+20으로 변경되어 계산된 값이 호출된다.

<br>

---

<br>

## :pencil:_Lesson 06. 변수를 활용한 데이터 중복 제거 및 재사용_

- 변수의 가장 큰 힘은 **데이터 재사용성**에 있다.

<br>

#### :exclamation: ​참고 하기 :exclamation:

```
document.write()메서드는 웹페이지에 html 태그를 출력해주는 기능을 한다.
```

<br>

#### :memo:_예제 01)_ 변수 활용하기

- 딴동네님 대신 짱아님으로 출력되게 변경해주세요. 또한, 이름을 계속해서 변경할 예정이니 좀 쉽게 작업할 수 있게 만들어 주세요

```javascript
document.write("딴동네님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write("딴동네님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write("딴동네님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write("딴동네님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write("딴동네님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
```

- 풀이

```javascript
var name = "짱아";
document.write(name+"님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write(name+"님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write(name+"님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write(name+"님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
document.write(name+"님 안녕하세요. 자바스크립트 동네에 오신걸 환영합니다.", "<br>");
```

- 설명
  - 변수를 사용하지 않고 한다면 `"딴동네"`라는 글자를 모두 `"짱아"`로 변경해야한다. 
  - 이런 문제를 해결하기 위해서는 **`변수`**를 사용하면 쉽게 해결할 수 있다.
  - 변수에 변경할 데이터를 저장한 후 재상용함으로써 중복해서 해야 할 내용을 쉽게 처리할 수 있다.
  - 만약 다른 이름으로 또다시 변경해야한다면 `var name = "";`에 다른 값으로 변경하면 된다.

<br>

---

<br>

## :pencil:_Lesson 07. 변수에 어떤 값이 들어 있는지 확인하기_

- 변수 내부에 어떤 값이 저장돼 있는지 눈으로 확인하는 방법
  - alert()
  - document.write()
  - console.log()

<br>

### _01. alert()_

- alert() 함수는 특정 정보를 사용자에게 메시지 창으로 알려주기 위해 주로 사용한다.

<br>

- 문법

```javascript
alert(데이터);
```

- 설명
  - `alert()`에 확인하고 싶은 변수를 "데이터"에 넣어주면 된다.

<br>

#### :memo:_예제 01)_ name변수에 저장된 값을 alert() 함수를 이용해서 알림창으로 출력해 주세요 

```javascript
var name = "OHTAEKWON";
alert(name);
```

<br>

### _02. document.write()_

- `Document`라는 객체에서 제공하는 `write()`기능은 HTML 문서의 body 영역에 <div>와 같은 HTML 태그 내용을 출력해 준다.
- 브라우저 화면에 출력할 수 있는 기능 떄문에 주로 프로그래밍 문법 테스트용으로 사용된다.

<br>

- 문법

```javascript
document.write(데이터[, 데이터...]);
```

- 설명
  - `document.write()`에 확인하고 싶은 변수를 "데이터"에 넣어주면 된다.

<br>

#### :memo:_예제 02)_ name 변수에 저장된 값을 document.write()를 이용해서 문서 영역에 출력해 주세요. 

```javascript
var name = "OHTAEKWON";
document.write("name =" + name);
```

<br>

#### :memo:_예제 03)_ 이름과 나이가 담긴 변수 내용을 화면에 출력해 보아라.

```javascript
var name = "OHTAEKWON";
var age = 30;

document.write("name =" ,name, " age = ", age, "<br>");		//-----※1
document.write("name = " +name+ " age = " + age+ "<br>");	//-----※2
```

- 설명
  - `document.write()`를 이용해 변숫값을 확인할 때 `※1`처럼 `콤마(,)`를 이용해 데이터를 각각 넘겨도 되며 `※2`처럼 데이터를 하나의 문자열로 만들어 넘겨도 된다.

<br>

### _03. console.log()_

- 논리적인 오류인 버그라고 불리는 것들을 찾아 없애는 작업을 `디버깅`이라고 한다.
- **`console.log()`**기능은 **`전문 디버깅 도구`**
- **`console.log()`** 기능은 웹킷 엔진을 사용하는 브라우저인 크롬과 사파리에서만 사용 가능하며 출력 값은 모든 디버깅 기능을 가지고 있는 `인스팩터(Inspector)` 화면의 콘솔 영역에 출력된다.

<br>

- 문법

```javascript
console.log(데이터[, 데이터...]);
```

- 설명
  - `document.write()`와 같이 출력할 변수나 데이터를 "데이터" 부분에 넣어준다.

<br>

#### :memo:_예제 04)_ name변수에 저장된 값을 console.log()를 이용해서 웹킷 브라우저의 인스팩터 창으 ㅣ콘솔 영역에 출력해 보아라

```javascript
var name = "OHTAEKWON";
console.log("name = " +name)
```

<br>

### _04. 정리_

| 기능                           | 전문 디버깅 기능 | 주용도                                                       |
| ------------------------------ | :--------------: | ------------------------------------------------------------ |
| ***alert(변수이름)***          |        X         | 사용자에게 **특정 정보**를 **팝업 창**을 이용해 알려주고 싶을 때 사용한다. <br />자바스크립트 초보 시절 변숫값을 확인하기 위해 잠시 사용한다. |
| ***document.write(변수이름)*** |        X         | **<body>영역**에 HTML 태그 정보를 **출력**할 때 사용한다.<br />자바스크립트 초보 시절 변숫값을 확인하기 위해 잠시 사용한다. |
| ***console.log(변수이름)***    |        O         | **전문 디버깅 함수**로서 특정 **변수의 값을 확인**할 때 사용한다.<br />자바스크립트 초보 시절부터 계속해서 사용 |

<br>

---

<br>

## :pencil:_Lesson 08. 주석_

### _01. 주석이란? - 한 줄로 말해요_

- 코드에 대한 설명을 달아 놓기 위해 사용
- 다른 개발자와의 협업이나 유지보수를 위해 사용

<br>

### _02. 주석 만드는 방법 2가지_

- 한 줄 주석
- 여러 줄 주석

<br>

> **1) 한줄 주석 `/`**

```javascript
// 여기에 설명을 입력해주세요
```

<br>

> **2) 여러 줄 주석 `/* */`**

```javascript
/*

여기에 설명을 입력해 주세요.

*/
```

<br>

---

<br>

## :pencil:_Lesson 09. 배열_

### _01. 배열이란?_

- 일반 변수는 데이터를 하나만 저장할 수 있지만,
- 배열 변수는 변수 하나에 **`여러 개의 데이터`**를 담을 수 있는 데이터형이다.

<br>

> ***일반변수***

![](https://user-images.githubusercontent.com/75871005/125486595-5053de50-7ab9-4cc3-8544-7c9cd533deae.png)



> ***배열***

![](https://user-images.githubusercontent.com/75871005/125488477-7f9a532b-517c-4bf2-ac40-70226104e7e7.png)

> ***일반변수 vs 배열***

```javascript
// 일반 변수로 표현한 경우
var userName1 = "TK";
var userName2 = "BTS";
var userName3 = "SON";

// 배열로 표현한 경우
var userName = ["TK", "BTS", "SON"];
```

<br>

### _02. 배열 생성_

```javascript
var 변수이름 = [데이터[,...]];
```

- 설명
  - 배열 데이터를 만드는 방법은 대괄호`[ ]`에 데이터를 넣어 표현한다.
  - 데이터 항목은 콤마`,`를 이용해 구분한다.

<br>

#### :memo:_예제 01)_ "TK", "BTS", "SON" 이름 정보를 담은 배열 만들기

```javascript
var uesrName = ["TK", "BTS", "SON"];
```

<br>

#### :memo:_예제 02)_ 본인의 이름, 나이, 취미 정보를 담은 배열 만들기

- 배열에는 여러 개의 데이터형을 혼합해서 보관할 수 있다.

```javascript
var userInfo = ["TK", 30, "코딩"];
```

<br>

#### :exclamation: ​참고 하기 :exclamation:

- 다른 방법으로 배열하기

```javascript
var 변수이름 = new Array(데이터[,...]);
```

<br>

### _03. 배열 요소 접근_

```javascript
배열이름[n];
```

- `n`은 배열 요소의 **index**를 나타낸다.
  - ***값은 0부터 시작해 배열 크기 -1까지의 값을 갖는다.***

<br>

#### :memo:_예제 03)_  다음 배열 요소를 하나씩 출력해 보시오.

```javascript
var userName = ["OHTAEKWON", "BTS", "SON", "GD", "TK", "민수", "태현", "태준"];

/////////////////////////////////////
document.write("userName[0] = " + userName[0], "<br>");		// userName[0] = OHTAEKWON
document.write("userName[1] = " + userName[1], "<br>");		// userName[1] = BTS
document.write("userName[2] = " + userName[2], "<br>");		// userName[2] = SON		
document.write("userName[3] = " + userName[3], "<br>");		// userName[3] = GD
document.write("userName[4] = " + userName[4], "<br>");		// userName[4] = TK
document.write("userName[5] = " + userName[5], "<br>");		// userName[5] = 민수
document.write("userName[6] = " + userName[6], "<br>");		// userName[6] = 태현
document.write("userName[7] = " + userName[7], "<br>");		// userName[7] = 태준
```

- 설명
  - ***n은 배열 `인덱스 값`을 의미하며, 인덱스 값은 0부터 시작한다.***
  - **`인덱스 값`**을 이용해 배열에 저장되어 있는 정보에 접근할 수 있다.

<br>

---

<br>

## :pencil:_Lesson 10. 변수 종류_

### _01. 변수 종류_

- 변수는 사용 범위에 따라 총 4개의 변수로 나뉜다.

| 변수                   | 설명                                                         |
| ---------------------- | ------------------------------------------------------------ |
| **전역변수**           | 전역에서 사용하는 데이터를 담는 변수이며 어디서든 접근해서 사용이 가능하다 |
| **지역변수**           | 특정 영역에서만 사용할 수 있는 변수이며, 주로 함수 내부에 만들어지는 변수이다. |
| **매개변수(파라미터)** | 함수 외부에서 함수 내부로 데이터를 전다하기 위한 용도로 사용하는 변수이다. |
| **멤버변수(프로퍼티)** | 클래스 내부에 만들어지며 주로 객체에서 사용하는 정보를 담는 변수이다. |

<br>

### _02. 전역변수_

```javascript
var globalV = "전역변수"; //----------※1

window.onload=function(){
    global2 = "전역변수"; //----------※2
}
function func1(){
    var local = "지역변수"; //----------※3
}
```

- `※1` 이 위치의 변수는 모두 **전역변수**이다.
- `※2` 함수 내부에서 var 없이 변수에 값을 대입하면 전역변수로 만들어진다. 
  - 즉, `global2 = "전역변수";` 는 window.global2="전역변수"와 같다.
- `※3` local1은 **지역변수**이다.

<br>

### _03. 지역변수_

```javascript
var globalV = "전역변수";

window.onload=function(){
    var local1 = "지역변수"; //----------※1
}
function func1(){
    var local1 = "지역변수"; //----------※2
}
function func2(){
    document.write(globalV);
}
```

- `※1` local1은 지역변수이며 오직 `onload()`함수 영역에서만 사용할 수 있다.
- `※2` local1 역시 `func1`에서만 사용할 수 있는 **지역변수**이다. `※1` 과 변수 이름이 같더라도 다른 영역에서 만들어진 변수이기 떄문에 완전히 다른 변수이다.

<br>

### _04. 매개변수_

```javascript
var globalV = "전역변수";

window.onload=function(){
    var local1 = "지역변수";
    func1(100, 200);
}
//------------ ※1 , ※2
function func1(num1, num2){
    var local1 = "지역변수";
    
    document.write("매개변수 num1= "+num1+", num2="+num2");
}
```

- `※1` , `※2` 는 **매개변수** 또는 **파라미터**라고 부른다. 주로 **함수 외부에서 함수 내부로** 데이터를 전달할 때 사용한다.
- ***매개변수는 지역변수와 마찬가지로 함수 내부에서만 사용할 수있다.***

<br>

### _05. 멤버변수_

```javascript
function MyClass(){
    this.name = "멤버변수"; //----------※1
}
MyClass.prototype.showName=function(){ //----------※2
    document.write("name = ", this.name);
}
var objClass = new MyClass();
objClass.showName();
```

- `※1` 변수처럼 name이 있는데, 이 변수를 **멤버변수**라고 부른다. 
  - 이 변수는 `MyClass`라는 클래스에서 만들어지고 사용하기 떄문에 멤버변수라고 부른다.
- `※2` 는 **멤버함수** 또는 **메서드**라고 부른다. 

<br>

---

<br>