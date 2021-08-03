# _CHAPTER 10 - 함수 중급_

<br>

## :speaker: INTRO

<br>

## :information_source:INDEX

|     Lesson      |           Content           |
| :-------------: | :-------------------------: |
| ***Lesson 01*** |  **변수와 함수와의 관계**   |
| ***Lesson 02*** | **함수 리터럴과 익명 함수** |
| ***Lesson 03*** |  **함수 정의 방법 4가지**   |
| ***Lesson 04*** |        **함수 종류**        |
| ***Lesson 05*** |        **중첩 함수**        |
| ***Lesson 06*** |        **콜백 함수**        |
| ***Lesson 07*** |       **클로저 함수**       |
| ***Lesson 08*** |          **미 션**          |

<br>

---

<br>

## :pencil:_Lesson 01. 변수와 함수와의 관계_

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/10.01_1.png?raw=true)

<br>

### _01. 변수에 함수 저장하기_

_초보자의 경우 변수를 사용할 때 숫자, 문자, 불린 값만을 넣는 예제를 주로 다루기 때문에 변수에 함수를 넣는다는 개념을 이해하지 못하는 경우가 있다._

***함수 역시 변수에 넣을 수 있는 데이터 값이다.***

예를 들어 변수에 문자열을 넣는 것처럼, 변수에 함수라는 데이터를 넣을 수 있다.

#### :memo:_예제 01)_ 변수에 함수를 저장한 경우

```javascript
function hello(name){
    document.write(name+"님 환영합니다.");
}
hello("자바스크립트");	// 자바스크립트님 환영합니다.
var func = hello;
func("프론트엔드");		// 자바스크립트님 환영합니다.
```

##### 💻 실행결과

​	자바스크립트님 환영합니다.
​	자바스크립트님 환영합니다.

<br>

:pencil: **설명**

​	***예제처럼 변수에 함수를 저장하면 변수를 함수처럼 사용할 수있다.***

<br>

### _02. 매개변수 값으로 함수 사용하기_

`매개변수`또한 변수이기 때문에 `매개변수` 값으로 함수를 사용할 수 있다는 의미와도 같다.

<br>

#### :memo:_예제 02)_ 매개변수 값으로 함수를 사용한 경우

```javascript
function hello(){
    alert("hello");
}
function hello2(){
    alert("안녕하세요.");
}
function execute(func){
    func();
}
execute(hello);		// hello
execute(hello2);	// 안녕하세요.
```

##### 💻 실행결과

​	hello
​	안녕하세요.

<br>

:pencil: **설명**

​	***예제처럼 함수를 매개변수 값으로 넘겨 매개변수를 일반 함수처럼 사용할 수 있다.***

<br>

#### :memo:_예제 03)_ 버튼을 클릭할 때마다 매개변수 값으로 넘긴 hello 함수가 호출한다.

```javascript
function hello(){
    document.write("안녕하세요. 환영합니다.");
}
$("btnStart").click(hello);
```

- _버튼을 클릭하면 `hello메서드`의 값을 반환한다._

<br>

#### :memo:_예제 04)_ 1초마다 매개변수 값으로 넘긴 익명 함수가 호출된다.

```javascript
setInterval(function(){
    document.write("안녕하세요. 환영합니다.<br>");
}, 1000);

/*
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
안녕하세요. 환영합니다.
.....
*/
```

<br>

### _03. 리턴값으로 함수 사용하기_

_함수는 어떤 값(데이터)이든 리턴할 수 있다._ 이는 리턴값으로 함수를 리턴할 수 있다는 의미이기도 한다.

<br>

#### :memo:_예제 05)_ 리턴값으로 함수를 사용한 경우

```javascript
function createHello(){
    function hello(user){
        document.write(user+"님 방문을 환영합니다.")
    }
    return hello;	// 리턴값으로 hello함수를 사용
}
var result = createHello();
result("프론트엔드");	// 프론트엔드님 방문을 환영합니다.
```

##### 💻 실행결과

​	프론트엔드님 방문을 환영합니다.

<br>

:pencil: **설명**

​	***createHello() 함수 내부에 있는 hello() 함수를 리턴값으로 하면 함수 외부에서 사용할 수 있게 된다.***

- `return` 값을 hello 함수로 출력
- `createHello()`함수를 result의 변수 값으로 사용하고 result를 파라미터로 `createHello`를 사용하여 `hello`의 user의 매개변수로 입력되며, 최종적으로 `user+"님 방문을 환영합니다."`이 반환된다.
  즉, **프론트엔드님 방문을 환영합니다.**가 출력이 된다.

<br>

---

<br>

## :pencil:_Lesson 02. 함수 리털럴과 익명 함수_

다음 코드는 아의 예제들에서 무수히 많은 사용한 익명 함수(이름이 없는 함수)를 이벤트 리스너로 등록한 예제이다.

```javascript
$("btnStart").click(function(){
    alert("안녕하세요. 환영합니다.");
})
```

- 여기서 `이벤트리스너`란 ***이벤트가 발생할 때 실행되는 함수를 의미한다.***

<br>

### _01. 리터럴이란?_

데이터를 만드는 방법은 크게 `리터럴 방식`과 `객체 방식` 두 가지가 있다.

여기서 `리터럴`이란 **원시**라는 뜻을 가지고 있다.

<br>

#### :diamonds: 리터럴 방식과 객체 방식의 차이 :diamonds:

|   타입   | 리터럴 방식                                | 객체 방식                                           |
| :------: | :----------------------------------------- | --------------------------------------------------- |
| **숫자** | var age = 10;                              | var name = new Number(10);                          |
| **문자** | var name = "OHTAEKOWN"                     | var name = new String("OHTAEKWON");                 |
| **불린** | var cold = true;                           | var cold = new Boolean(true);                       |
| **배열** | var anyDate = ["data1", "data2", "data3"]; | var anyDate = new Array("data1", "data2", "data3"); |

일반적으로 실무에서는 **숫자데이터**나 **문자데이터** 그리고 **배열데이터**같은 기본적인 데이터를 생성할 때 리터럴 방식을 더 많이 사용한다. 왜냐하면, ***리터럴 방식이 훨씬 더 간결하고 편리하기 때문이다.***

예를 들어 숫자 10을 가진 변수를 만들 때, `var a = 10`의 리러털 방식 대신 `var a = new Number(10)`식의 객체 방식으로 만든단고 하면, 만들때마다 힘들어진다.

자바스크립트 엔진에서는 `var a = 10`을` var a = new Number(10)`로 자동변환이 되어 실행된다.

<br>

### _02. 함수 리터럴이란?_

함수 역시 리터럴 방식으로 함수를 만드는 방법을 제공한다. 함수 리터럴 방식으로 함수를 만드는 방법

<br>

#### :memo:_예제 01)_ 함수 만드는 방법 3가지

| 리터럴 방식                                                  | 일반적인 방식과 객체 방식                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| var hello = function(name){<br />       alert(name + "님 환영합니다.")<br />}<br />hello("OHTAEKWON"); | // 일반적인 방식<br />function hello(name){<br />        alert(name + "님 환영합니다. ");<br />}<br />hello("OHTAEKWON");    // OHTAEKWON님 환영합니다.<br /><br />// 객체 방식<br />var hello2 = new Function("name","alert(name+'님 환영합니다.');");<br />hello2("OHTAEKWON"); |

:exclamation: 질문 

함수의 경우는 사용하려는 용도에 따라 리터럴 방식과 일반적인 방식을 같이 사용하기 때문에 무조건 리터럴 방식으로 만들진 않는다.

그리고 함수 리터럴 방식으로 만들어진 이름없는 함수를 **익명 함수**라고 한다.

<br>

### _03. 함수 리터럴이란?_