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


