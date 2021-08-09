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

### _03. 익명 함수란?_

<br>

#### :one: 익명 함수 풀이 버전

**익명함수**란? 함수 리터럴 방식으로 만들어진 이름 없는 함수를 말한다. 이벤트 처리 등에 익명 함수를 활용하면 더 간결하게 만들 수 있다.

<br>

#### :memo:_예제 02)_ 익명함수 활용

| 익명 함수 활용 전                                            | 익명 함수 활용 후                                            |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| function hello(){<br />        alert("안녕하세요. 환영합니다.");<br />}<br />$("#btnStart").click(hello); | $("btnStart").click(function(){<br />        alert("안녕하세요. 환영합니다.");<br />}) |

<br>

#### :two: 익명 함수 vs. 일반 함수

_함수를 만들 때 어떤 경우에 익명함수로 만들고 어떤 경우에 일반 함수로 써야 하는가?_

- 함수를 익명함수로 만드는 경우 **(주로 함수를 재사용하지 않을 경우)**

  ```javascript
  $("btnStart").click(function(){
      alert("안녕하세요. 환영합니다.");
  });
  ```

  - `click()`의 매개변수로 넘어 간 익명 함수는 click이벤트 리스너 함수로만 사용할 뿐 이름이 없기 때문에 함수를 다시 호출하고 싶어도 호출할 방법이 없다.
  - _이와 달리 함수를 일방 방식으로 만들면,_

  ```javascript
  function hello(){
      alert("안녕하세요. 환영합니다.");
  }
  $("btnStart").click(hello);
  ```

  - ***이름이 있는 함수이기 때문에 언제든지 hello() 함수를 호출해서 재사용할 수 있다.***

<br>

#### :memo:_예제 03)_ 버튼을 클릭할 때마다 횟수와 함께 "안녕하세요. 환영합니다." 메시지를 #info에 출력해주세요.

#### (단, 페이지가 실행되면 바로 '0 안녕하세요. 환영합니다.'메시지가 출력되어야 합니다.)

##### 💻 실행결과

```javascript
0 안녕하세요. 환영합니다.  	// ← 버튼 클릭 전에 출력되어야 한다.
1 안녕하세요. 환영합니다.		// ← 이 내용부터는 버튼 클릭 후 출력된다.
2 안녕하세요. 환영합니다.
. . . . . 
```

<br>

:ballot_box_with_check: **풀이 전 코드 : 소스**

```html
<!DOCTYPE HTML>
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title> </title>
    <style>
        #info {
            border:1px solid #000;
            min-height:100px;
        }
    </style>
    <script src="../../libs/jquery-1.11.0.min.js"></script>
        
    <script>
        /*
         예제03: 버튼을 클릭할 때마다 클릭한 횟수와 함께 “안녕하세요. 환영합니다.” 메시지를 #info에 출력해 주세요.
         단, 페이지가 실행되면 바로 '0 안녕하세요. 환영합니다.' 메시지가 출력돼야 합니다.

         실행결과:
             0 안녕하세요. 환영합니다.   버튼 클릭 전에 출력돼 있어야 해요.
             1 안녕하세요. 환영합니다.   이 내용부터는 버튼 클릭 후 출력됩니다.
             2 안녕하세요. 환영합니다.
             . . . . .

        */

        var count=0;
        var $info = null;

        $(document).ready(function() {
            $info = $("#info");

            $info.append("<p>"+count+" 안녕하세요. 환영합니다.</p>");
            count++;
            $("#btnStart").click(function(){

                $info.append("<p>"+count+" 안녕하세요. 환영합니다.</p>");
                count++;
            });

        });

    </script>

</head>	
<body>
    <button id="btnStart">출력</button>
    <div id="info">
        
    </div>
</body>
</html>

```

<br>

---

<br>

## :pencil:_Lesson 03. 함수 정의 방법 4가지_

함수 정의, 즉 함수를 만드는 방법은 일반 방법 이외에 3가지 더 있다.

<br>

### _01. 첫 번째 : function 키워드를 이용하는 방법_

:pencil: **문법**

```javascript
function 함수이름([매개변수1, . . . .,]){
    [return 반환값]
}
함수이름(매개변수 값, . . . )
```

<br>

#### :memo:_예제 01)_ 일반적인 함수 정의

```javascript
function hello(name){
    document.write(name + "님 환영합니다.");
}
hello("OHTAEKWON");
```

<br>

### _02. 두번째 : 함수 리터럴을 이용하는 방법_

:pencil: **문법**

```javascript
var 변수이름 = function([매개변수1, . . . .]){
    [return 반환값]
}
변수이름(매개변수 값, . . . .);
```

<br>

#### :memo:_예제 02)_ 함수 리터럴을 이용한 함수 정의

```javascript
var hello = function(name){
    document.write(name +"님 환영합니다.");
}
hello("OHTAEKWON");
```

<br>

### _03. 세번째 : Function 객체를 이용해서 정의하는 방법_

:pencil: **문법**

```javascript
var 변수이름 = new Function([매개변수1....], 함수본체);
함수이름(매개변수 값,. . . . .);
```

<br>

#### :memo:_예제 03)_ 객체 방식을 이용한 함수 정의

```javascript
var hello = new Function("name","document.write(name+'님 환영합니다.')");
hello("OHTAEKWON");
```

:pencil: **설명**

_이 방법은 실무에서 거의 사용하지 않는다._
그냥 이런 식으로도 함수를 만드는 방법이 있구나라는 정도로 넘어가면 된다.

<br>

### _04. 네 번째 : 익명 함수 확장을 이용해 정의하는 방법_

:pencil: **문법**

```javascript
(function(매개변수1....){})(
	[return 반환 값]
)(매개변수 값);
```

<br>

#### :memo:_예제 04)_ 익명함수 확장을 이용한 함수 정의

```javascript
(function(name){
    document.write(name+"님 환영합니다.");
})("OHTAEKWON");	// OHTAEKWON님 환영합니다.
```

:pencil: **설명**

이 방법은 익명 함수의 확장이다. 이 정의 방법은 함수를 만들어 재사용하는 것이 목적이 아닌 다른 함수 간의 충돌을 막기 위해서 사용한다. 또한, jQuery 플러그인 제작 시 다른 플러그인과 충돌을 막기 위한 방법으로 많이 사용한다.

<br>

---

<br>

## :pencil:_Lesson 04. 함수 종류_

함수는 개발자가 직접 만들어서 사용하는 사용자 정의 함수와 자바스크립트에서 제공하는 코어 라이브러리로 나눌 수 있다. 

### _01. 함수 분류_

_함수는 크게 두 가지 분류로 나눌 수 있다._

:one: **사용자 정의 함수**

사용자가 필요한 기능을 직접 만든 함수를 말하며 앞의 예제들에서 직접 만든 함수가 모두 사용자 정의 함수이다. 

<br>

:two: **자바스크립트 코어 함수**

자바스크립트가 기본적으로 제공하는 함수를 코어 함수라고 하며 1부 2장 형변환에서 사용한 `parserInt()`, `parseFloat()` 함수 등이 자바스크립트 코어 함수에 속한다.

<br>

### _02. 사용 방법에 따른 함수 종류_

함수는 사용 방법에 따라 다음과 같이 나눌 수 있다.

|       함수 종류        | 내용                                                         |
| :--------------------: | ------------------------------------------------------------ |
|       일반 함수        | 가장 일반적으로 사용한 함수를 말한다.                        |
|       중첩 함수        | 함수 안에 함수가 있는 경우 중첩되었다라고 하며 이때 함수 안에 있는 함수를 중첩 함수라고 한다. |
|       콜백 함수        | 함수 실행결과값을 리턴이 아닌 매개변수로 넘어온 함수를 호출해서 넘겨주는 방식을 콜백이라하며 이때 매개변수로 넘어온 콜백 함수라고 한다. |
|      클로저 함수       | 일반적인 함수의 경우 함수 호출에 의해 함수 내부의 실행구문을 모두 실행하게 되면 함수 내부에서 만든 지역변수가 자동으로 사라라지만 어떤 경우에는 사라지지 않고 남는 겨웅가 있다.<br />이 현상을 클로저라고 하며 이 현상을 일으키는 함수를 클로저 함수라고 한다. |
| 멤버함수<br />(메서드) | 멤버함수는 클래스 내부에 만들어지며 주로 메서드로 불린다.    |

<br>

---

<br>

## :pencil:_Lesson 05. 중첩 함수_

### _01. 중첩함수란?_

***함수 내부에는 일반 구문뿐 아니라 새로운 함수 구문까지도 넣을 수 있다.*** 이때 함수 내부에 만들어지는 함수를 중첩함수라고 부른다.

```javascript
function outer(){
    // inner를 중첩 함수라고 부른다.
    function inner(){
        
    }
    inner();
}
outer();
```

_함수 내부에는 중첩 함수를 하나 이상 만들 수 있다._

<br>

### _02. 중첩 함수는 이럴 때 사용해요_

:one: **내부 전용 함수**

`중첩 함수`는 **함수 내부의 지역변수처럼 함수 내부에서만 사용할 수 있다.** 즉, 함수 내부에서만 사용하는 기능을  `중첩 함수`로 만들어 사용하는 것이다. 

일반적으로 `중첩 함수`는 다음과 같이 이름이 없는 `이벤트 리스너`로 많이 사용된다.

<br>

#### :memo:_예제 01)_ 1초에 한 번씩 "안녕하세요."를 출력해 주세요.

```javascript
function startHello(){
    var count = 0;
    setInterval(function(){
        count++;
        doucment.write(count+" 안녕하세요. ", "<br>");
    }, 1000)
}
startHello();
```

:pencil: **설명**

위의 풀이에도 클릭 이벤트 리스너가 중첩 함수로 사용되었다.
<br>

:two: **중복 코드 또는 코드 그룹화**

함수 내부의 커다란 기능이나 중복 코드를 `내부 함수`로 만들어 재사용할 때도 `중첩 함수`를 사용한다. 예를 들어 2장 미션에서 만든 `탭메뉴`의 커다란 기능을 여러 개의 중첩 함수로 나눠 만들면 다음과 같이 좀더 구조적으로 만들 수 있다.

- `중첩함수`를 활용한 `탭메뉴`는 미션에서 직접 만들어 볼 것이다.

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/10.05_1.png?raw=true)

<br>

#### :memo:_예제 03)_ 중첩 함수를 이용해 사칙연산 계산기를 만드시오.

:one: **변경 전**

```javascript
function calculator(op, num1, num2){
    var result="";
    
    switch(op){
        case "+":
            result=num1+num2;
            break;
        case "-":
            result=num1-num2;
            break;
        case "*":
            result=num1*num2;
            break;
        case "/":
            result=num1/num2;
            break;
        default:
            result="지원하지 않는 연산자입니다.";
    }
    return result;
}
document.write("1 결과 =" + calculator("+",20,10),"<br>");	// 1 결과 =30
document.write("2 결과 =" + calculator("-",20,10),"<br>");	// 2 결과 =10
document.write("3 결과 =" + calculator("*",20,10),"<br>");	// 3 결과 =200
document.write("1 결과 =" + calculator("/",20,10),"<br>");	// 4 결과 =2
```

<br>

:two: **변경 후**

```javascript
function calculator(op, num1, num2){
    var result="";
    
    switch(op){
        case "+":
            result=num1+num2;
            break;
        case "-":
            result=num1-num2;
            break;
        case "*":
            result=num1*num2;
            break;
        case "/":
            result=num1/num2;
            break;
        default:
            result="지원하지 않는 연산자입니다.";
    }
    return result;

    function add(num1,num2){
        return num1+num2;
    }

    function sub(num1,num2){
        return num1-num2;
    }

    function mul(num1,num2){
        return num1*num2;
    }

    function div(num1,num2){
        return num1/num2;
    }
}
```

<br>



### _03. 중첩함수와 중첩 함수를 포함한 함수와의 관계_

중첩 함수의 가장 큰 특징은 중첩 함수에서는 중첩 함수를 포함하고 있는 함수의 지역변수에 접근해서 사용할 수 있다.

#### :memo:_예제 04)_ 다음 코드를 실행하면 1번, 2번, 3번에는 어떤 값이 출력되는가?

```javascript
	var a = 10;
    var b = 20;
    var c = 30;
    function outer_func(){
        var b = 200;
        var c = 300;
        function inner_func(){
            var c = 3000;
            document.write("1. a = "+a+"<br>");	//--------------------(※1)
            document.write("2. a = "+b+"<br>");	//--------------------(※2)
            document.write("3. a = "+c+"<br>");	//--------------------(※3)
        }
        inner_func();
    }
    outer_func()   
```

##### 💻 풀이

```javascript
1. a = 10
2. b = 200
3. c = 3000
```

:pencil: **설명**

`※1`, 이 실행되면 먼저 `inner_func()` 함수 내부에 있는 지역변수 목록에서 a변수를 찾게 된다. 만약 존재하지 않는 경우 `inner_func()`함수를 호출한 `outer_func()`함수의 지역변수 목록에서 a를 찾기 시작한다. 이곳에서도 존재하지 안흥면 자바스크립트 엔진은 `outer_func()` 함수를 호출한 전역변수 목록에서 변수 a를 찾기 시작한다.

따라서, ***출력되는 값은 전역 변수 a의 값 10이 출력된다.***

`※2`,도 역시 `※1`과 같은 방식으로 최근 함수가 호출된 순서대로 변수 b를 찾기 시작한다. 따라서, `outer_func()` 함수의 변수 b에 저장되어 있는 값인 `200`이 출력된다.

`※3`의 경우에도 동일한 방식으로 변수를 찾기 때문에 변수 c는 `inner_func()` 함수의 지역변수가 되어 3000이 출력된다.

***이처럼 중첩함수에서는 중첩함수 내부에 품고 있는 변수와 함수를 접근해서 사용할 수 있다.***

<br>

---

<br>

## :pencil:_Lesson 06. 콜백 함수_

### _01. 콜백함수란?_

:pencil: **문법**

```javascript
function 함수이름(callback){
    . . . .
    callback(결과);
}
```

`콜백 함수`는 주로 **함수 내부의 처리 결과값을 함수 외부로 내보낼 때 사용한다.** 
=  `return`문과 비슷한 기능을 한다고 생각하면 된다.

`콜백 함수`를 사용하는 하는 구조를 살펴보면 위의 문법처럼 **특정 함수의 매개변수 값으로 콜백 함수를 넘긴 후 처리 결과를 콜백 함수의 매개변수에 담아 콜백 함수를 호출**하는 구조를 가지고 있다. 이 구조를 사용하면 로직 구현 부분과 로직 처리 부분을 나눠 코딩할 수 있다. 

_따라서, 로직 구현 부분은 동일하고 로직 처리 부분을 다양하게 처리해야하는 경우 유용하게 사용할 수 있다._

![10.06_1 img](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/10.06_1.png?raw=true)

<br>

### _02. 예제_

#### :memo:_예제 01)_ 풀이 전 코드는 사칙연산 계산기이다. 풀이 전 코드를 요구사항에 맞게 출력될 수 있도록 수정하여라.

**요구사항**

- calculator1("연산자", 값1, 값2)을 실행하면, `"두 수의 합은 00입니다."`를 출력하시오.
- calculator2("연산자", 값1, 값2)을 실행하면, `"정답은 00입니다."`를 출력하시오.

:ballot_box_with_check: **풀이 전 코드 : 소스**

```javascript
// 사칙연산 함수
function calculator(op, num1, num2){
    var result = "";
    
    switch(op){
        case "+":
            result = num1+num2;
            break;
        case "-":
            result = num1-num2;
            break;
        case "*":
            result = num1*num2;
            break;
        case "/":
            result = num1/num2;
            break;
        default :
            result = "지원하지 않는 연사자입니다."
    }
    document.write("두 수의 합은"+result+"입니다.","<br>");
}
calculator("+",10,20);		// 두 수의 합은30입니다.
```

<br>

:one: **일반 풀이**

```javascript
// 사칙연산 함수
function calculator1(op, num1, num2){	//------------------(※1)
    var result = "";
    
    switch(op){
        case "+":
            result = num1+num2;
            break;
        case "-":
            result = num1-num2;
            break;
        case "*":
            result = num1*num2;
            break;
        case "/":
            result = num1/num2;
            break;
        default :
            result = "지원하지 않는 연사자입니다."
    }
    document.write("두 수의 합은"+result+"입니다.","<br>");
}

function calculator2(op, num1, num2){	//------------------(※2)
    var result = "";
    switch(op){
        case "+":
            result = num1 + num2;
            break;
        case "-":
            result = num1 - num2;
            break;
        case "*":
            result = num1*num2;
            break;
        case "/":
            result = num1/num2;
            break;
        default :
            result = "지원하지 않는 연산자입니다.";
    }
    document.write("정답은 = "+result+"입니다.<br>"); //------------------(※3)
}

calculator1("+",10,20); //------------------(※4)
calculator2("+",10,20);

// 두 수의 합은30입니다.
// 정답은 = 30입니다.
```

:pencil: **설명**

여러가지 방법이 있지만, 위의 풀이처럼 기존 코드를 복사한 후 로직 처리 부분만 수정해서 처리할 수 있다. 풀이를 간단히 설명하면,

- `※1` , 기존 코드에서 함수 이름을 `calculator`에서 `calculator1`으로 변경해준다.
- `※2`,  기존 코드를 그대로 복사한 후 함수 이름을 `calculator2`로 변경해준다.
- `※3` ,  출력 정보를 요구사항에 맞게 수정해준다.
- `※4`,  두 개의 함수를 호출해 준다.

<br>

:two: **콜백 함수사용 풀이**

```javascript
function calculator(op, num1, num2, callback){	//------------------(※1)
    var result = "";
    
    switch(op){
        case "+":
            result = num1 + num2;
            break;
        case "-":
            result = num1 - num2;
            break;
        case "*":
            result = num1 * num2;
            break;
        case "/":
            result = num1 / num2;
            break;
        default :
            result = "지원하지 않는 연산자입니다.";            
    }
    callback(result);	//------------------(※2)
}

function print1(result){	//------------------(※3)
    document.write("두 수의 합은 = " + result + "입니다.","<br>");
}

function print2(result){	//------------------(※4)
    document.write("정답은 = "+result+"입니다. <br>");
}
calculator("+", 10, 20, print1);	//------------------(※5)
calculator("+", 10, 20, print2);	//------------------(※6)
```

:pencil: **설명**

- `※1`, 먼저 `calculator()`함수 마지막 부분에 콜백 함수로 사용할 함수를 저장할 `callback`이라는 이름을 가진 매개변수를 추가해 준다. 
  - function calculator(op, num1, num2, callback)
  - 참고로 매개변수 이름을 반드시 `callback`으로 하지 않아도 된다.
- `※2`, 기존 로직 부분을 주석처리한 후 결과값을 callback 함수에 넣어 호출해준다.
- `※3`, 신규로 `print1()`을 만들어 `calculator1`의 로직 처리 부분을 넣어준다.
- `※4`, 신규로 `print2()`를 만들어 `calculator2`의 로직 처리 부분을 넣어준다.
- `※5`, `※6` 마지막으로 `print1()` 함수와 `print2()` 함수를 매개변수로 값으로 해서 `calculator()` 함수를 각각 호출해준다.

_이처럼, 콜백함수를 이용하면 로직 처리 부분을 분리해 구현할 수 있다._
따라서, 처리부분을 수정해야하는 경우 로직 부분을 전혀 수정할 필요 없이 처리 부분만 수정하면 된다.

<br>

### _03. return vs. 콜백함수_

_콜백 함수를 이용하면 리턴값이 있는 함수 구문을 대신 사용할 수 있다._

| 리턴값이 있는 함수 구문                                      | 콜백 함수 구문                                               |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| function 함수이름(){<br />   . . . . . <br />   return 결과;<br />} | fucntion 함수이름(callback){<br />     . . . . . .<br />     callback 결과;<br />} |

:pencil: **설명**

- 실행 결과는 두 가지 방법 모두 동일하다. 하지만, 단순한 처리는 `리턴`으로 이용하는 것이 더 효율적이며
- 처리 부분이 구현 부분과 분리되어야 하는 경우나 구현 부분은 하나로 하고 처리 부분을 다양하게 만든 후 실행을 해야할 경우에는 `콜백`함수를 이용하는 것이 적합하다.

<br>

### _04. 동기 vs. 비동기_

_콜백 함수를 확실히 이해하기 위해서는 `동기`와 `비동기`를 이해해야한다._

:one: **동기란**

일반적으로 함수가 호출된 후 끝날 떄까지 다음 구문을 실행하지 않고 대기하고 있는 경우를 `동기`라고 부른다.

즉, ***특정 동작이 완료될 때까지 기다리고 다음 동작을 하는 것***을 말한다.

<br>

#### :memo:_예제 03)_ 동기 테스트.

```javascript
alert("안녕하세요.");	//------------------(※1)
document.write("alert() 동작이 끝나야 이 내용은 실행된다.");	//------------------(※2)
```

:pencil: **설명**

- `※1`, alert() 함수가 실행되면 알림 메시지 창이 활성화되는데 이때 알림 메시지 창의 확인 버튼을 눌러야지만 다음 구문인 `※2`가 실행된다.
  - 이처럼 **특정 동작이 완료될 때까지 기다리는 경우**를 `동기방식`이라고 한다.

<br>

:two: **비동기**

비동기는 동기와 반대되는 개념이다. 
_일반적으로 함수가 호출된 후 끝날 떄까지 기다리지 않고 바로 다음 구문을 실행하는 경우를 `비동기`라고 부른다._

#### :memo:_예제 04)_ 비동기 테스트.

```javascript
var count=1;

setInterval(function(){	//------------------(※1)
    documnet.write("2. count = " + count);
},3000);

document.write("1. ajax() 동작이 모두 끝나지 않았어도 바로 실행된다.");	//------------------(※2)
```

:pencil: **설명**

- `setInterval()`함수는 특정 시간마다 첫 번째 매개변수 값으로 넘긴 함수(콜백)를 호출해주는 기능을 가진 자바스크립트 코어 라이브러리 함수 중 하나이다.
- `※1`의 `setInterval()`함수가 실행되면 자바스크립트 엔진은 동기 함수와 달리 3초를 기다리지 않고 바로 다음 구문인 `※2`구문을 실행하여 메시지가 출력된다.
- 이 후 `setInteval()` 첫 번째 매개변수 값으로 넘긴 콜백 함수는 3초후에 실행된다.

_이처럼 특정 동작이 완료될 때까지 기다리지 않고 바로 다음 구문을 실행하는 경우를 `비동기 방식`이라고 부른다._

***콜백 함수가 주로 비동기 함수의 결과값을 처리하기 위한 도구로 많이 사용된다.***

<br>

### _05. 콜백 함수는 실무에서 이렇게 사용한다._

#### 1) 이벤트 리스너로 사용

_jQuery에서 클릭과 같은 이벤트를 처리하기 위해 등록하는 이벤트 리스너가 바로 콜백함수이다._

<br>

#### 2) 타이머 실행 함수로 사용

<br>

#### 3) Ajax 결과값을 받을 때 사용

_서버와 데이터를 주고받을 때 사용하는 jQuery Ajax 기능들에서 결과물을 받을 때 콜백 함수가 사용된다._

<br>

#### 4) jQuery 애니메이션 완료

<br>

---

<br>

## :pencil:_Lesson 07. 클로저 함수_

### _01. 클로저란?_

클로저는 함수 내부에서 만든 지역변수가 사라지지 않고 계속해서 값을 유지하고 있는 상태를 말한다.

```javascript
function func(){
    var count = 1;	// 일반 지역 변수의 겨웅 함수 호출이 완료되면 사라진다.
    
    /*
    	클로저를 이용하면 함수호출 완료 후 
    	사라지는 지역변수를 사라지지 않는 
    	데이터 저장소로 만들 수가 있다.
    */
    
    $("#btn").on("clock",
      function(){
        count++;
        alert("count = "+count);
    }
  );
}
```

:pencil: **문법**

```javascript
function 외부함수(){
    var 변수A;
    function 내부함수(){
        변수A 사용;
    }
}
```

클로저는 일종의 현상이기 때문에 정해진 문법은 없다. 위의 문법처럼 **내부함수**에서 **내부함수를 포함하고 있는 함수(외부함수)의 변수A**를 사용하는 구조인 경우로 표현할 수 있으며 **내부 함수를 클로저 함수라고 부른다.**

또한, _변수A는 클로저 현상에 의해 외부함수() 호출이 끝나더라도 사라지지 않고 값을 유지하게 된다._

<br>

### _02. 예제_

#### :memo:_예제 01)_ 일반 함수인 경우

```javascript
function addCount(){
    var count=0;
    count++;
    return count;
}

document.write("1. count = "+addCount(),"<br>");	//------------------(※1)
document.write("2. count = "+addCount(),"<br>");	//------------------(※2)
document.write("3. count = "+addCount(),"<br>");	//------------------(※3)

// 실행결과
// 1. count = 1
// 2. count = 1
// 3. count = 1
```

:pencil: **설명**

- `※1` `addCount()` 함수가 호출되면 지역변수 count가 0으로 초기화 됨과 동시에 만들어진다. 다음으로 증가 연산자에 의해 1이 되며, 이 값을 리턴하기 때문에 **1이 출력된다.** **그리고 모든 구문을 실행한 함수는 종료된다.**
  이와 동시에 함수 내부에 만들어진 count는 메모리에서 흔적조차 없이 사라진다.
- `※2`, `※3` 역시 `※1`과 동일하게 실행되기 때문에 1이 출력된다.

_이처럼 일반적인 경우 함수 내부에 위치하고 있는 지역변수는 함수가 종료됨가 동시에 메모리에서 사라지게 된다._

<br>

#### :memo:_예제 02)_ 클로저를 사용한 경우

_클로저 함수의 경우에 지역변수가 사라지지 않고 계속해서 값을 유지한다._

```javascript
function createCounter(){
    var count=0;
    function addCount(){
        count++;
        return count;
    }
    return addCount;
}

var counter = createCounter();	//----------(※1)

document.write("1. count = "+ counter(), "<br>");	//----------(※2)
document.write("2. count = "+ counter(), "<br>");	//----------(※3)
document.write("3. count = "+ counter(), "<br>");	//----------(※4)

// 실행결과
// 1. count = 1
// 2. count = 2
// 3. count = 3
```

:pencil: **설명**

- `※1`, `createCounter()` 함수가 호출되면 지역변수 count가 0으로 초기화됨과 동시에 만들어진다. 
  그리고 내부에 `addCount()`라는 함수도 만들어지고, 마지막으로 `addCount()` 함수를 리턴하고 `createCounter()` 함수는 종료된다.
- `※2`에서 `counter()` 실행되면 `addCount()` 함수가 실행되어 증가 연산자에 의해서 count값이 0에서 1로 증가하기 때문에 1이 출력된다.
- `※3`, `※4` 둘 모두 `counter()`가 실행되면 count가 값이 증가하기 때문에 2와 3이 각각 출력된다.

<br>

`createCounter()`가 종료되더라도 `count`는 사라지지 않고 계속해서 값을 유지하고 있다. 이유는 `addCounter()` 함수 내부에 count변수를 사용하고 있는 상태에서 외부로 리턴되어 클로저 현상이 발생한다.

<br>

#### :memo:_예제 03)_ 버튼을 클릭하면 클릭할 때마다 1씩 증가시켜 보시오.

```javascript
$("#btnStart").click(function(){
    start();
    document.write("시작합니다.");
});

function start(){
    var count=0;	// 지역변수
    
    // 익명함수
    setInterval function(){
        count++;	// count값의 증가
        document.write(count);
    },1000);
}
```

<br>

