# _APPENDIX 01_ - 함수와 클래스

<br>

## :information_source:INDEX

|     Lesson      |  Content   |
| :-------------: | :--------: |
| ***Lesson 01*** |  **함수**  |
| ***Lesson 02*** | **클래스** |

<br>

## :pencil:_Lesson 01. 초보자를 위한 함수_

### _01. 함수란?_

- 함수는 `동전 교환기`와 같다.
  - ex) 1,000 투입 → 100원 10개 교환
- 함수는 특정 기능을 하는 `구문(알고리즘, 로직)`을 묶어 재사용하는 문법이다.

<br>

***EX) 함수를 그림으로 표현***

![](https://user-images.githubusercontent.com/75871005/125578161-50c6fd2e-dde3-403e-992c-0e9e8d083977.png)<br>

### _02. 함수는 이럴 때 사용한다._

> **1) 함수사용 전**

- 3단

```javascript
var dan = 3;
document.write(dan+ " X 1 = " +(dan*1), "<br>");
document.write(dan+ " X 2 = " +(dan*2), "<br>");
document.write(dan+ " X 3 = " +(dan*3), "<br>");
document.write(dan+ " X 4 = " +(dan*4), "<br>");
document.write(dan+ " X 5 = " +(dan*5), "<br>");
document.write(dan+ " X 6 = " +(dan*6), "<br>");
document.write(dan+ " X 7 = " +(dan*7), "<br>");
document.write(dan+ " X 8 = " +(dan*8), "<br>");
document.write(dan+ " X 9 = " +(dan*9), "<br>");
```

- 만약 4단, 5단, 6단, 7단, 8단, 9단 일일히 다 코드를 복사하고 붙여넣어주어야 하는 단점이 발생
- 일이 비효율적으로 된다. 이럴때 함수로 지정해주면 편리하다.

<br>

>**2)  함수사용 후**

```javascript
function print99DAN(dan){
    // 이곳에 특정 기능을 하는 구문이 위치하게 된다.
    document.write(dan+ " X 1 = " +(dan*1), "<br>");
    document.write(dan+ " X 2 = " +(dan*2), "<br>");
    document.write(dan+ " X 3 = " +(dan*3), "<br>");
    document.write(dan+ " X 4 = " +(dan*4), "<br>");
    document.write(dan+ " X 5 = " +(dan*5), "<br>");
    document.write(dan+ " X 6 = " +(dan*6), "<br>");
    document.write(dan+ " X 7 = " +(dan*7), "<br>");
    document.write(dan+ " X 8 = " +(dan*8), "<br>");
    document.write(dan+ " X 9 = " +(dan*9), "<br>");
}

print99DAN(3);
print99DAN(4);
print99DAN(5);
```

- 함수는 특정 기능을 하는 알고리즘을 재사용하기 위해 사용하는 포장기술로서,
- 중복되는 구구단 출력 알고리즘을 함수에 담아 적용시키면, 더욱 편리해진다.

<br>

### _03. 함수 생김새_

변수 `var`키워드를 사용한 것처럼 함수는 `function`키워드를 사용해서 만든다.![](https://user-images.githubusercontent.com/75871005/125580518-0c987ed8-d7c4-4b52-911a-6f86243da9bd.png) 

<br>

### _04. 함수 호출_

- 함수만 만든다고 함수가 자동으로 동작하지는 않는다.
- 함수를 동작시키기 위해서는 `함수호출` 이라는 것을 해야한다.
  - 방법
    - 함수 이름 다음에 `괄호`를 열고 닫고 해주면 된다.
    - ex) 함수이름(); / alert(), document.write(), console.log()

<br>

### _05. 매개 변수_

- 함수가 호출되어 실행되기 시작하면 함수 내부는 함수 외부에서 접근할 수 없게 된다.![](https://user-images.githubusercontent.com/75871005/125598028-139370b9-370e-42a5-a286-5ede1d46e73d.png)

- 이때 함수 외부에서 함수 내부로 값을 전달하는 방법은
  - **매개변수**를 이용하는 것.
    - 외부 데이터를 함수 내부로 전달하는 매개체 역할하는 변수![](https://user-images.githubusercontent.com/75871005/125627493-a37f3849-67d8-4aed-b8bf-3647826cd769.png)

- 함수를 호출하면 `데이터`가 `매개변수1`로 넘어간다.
- 즉, `매개변수1 = 데이터` 와 같게 되는 것이다.

<br>

- 매개변수의 위치는 다음과 같이 괄호 안에 위치한다.![](https://user-images.githubusercontent.com/75871005/125628085-77ce9f2d-6725-4378-9ac9-bd35ff15ea92.png)
- 매개변수는 함수에 따라 없을 수도 있고 1개 이상 있을 수도 있다.

<br>

### _06. 리턴값_

- 리턴값은 매개변수와 반대의 개념이라고 보면 된다.![](https://user-images.githubusercontent.com/75871005/125629020-7b963dd3-f6d9-4e3f-b886-edb72ac96e72.png)
- `매개변수`는 **함수 외부에서 함수 내부**로 데이터를 전달하기 위해 사용하는 통로지만,
- `리턴값`은 **함수 내부에서 함수 외부**로 데이터를 보내기 위해 사용하는 통로이다.

```javascript
var 변수이름 = 함수이름([매개변수1값. . . .]);
```

<br>

***EX) 두 수의 합을 계산해 외부로 알려주는 sum()이라는 함수에서 리턴값***

![](https://user-images.githubusercontent.com/75871005/125631605-11231c92-6880-40a0-ad4e-0135bfb99638.png)

<br>

### _07. 함수 종류_

- 함수는 크게 자바스크립트 `코어 함수`와 `사용자 정의 함수` 두 가지로 나뉜다.

> **1) 자바스크립트 콩어 함수(라이브러리)**

- 자바스크립트에서는 가장 기본이 되는 기능을 미리 구현해 제공해준다.
- 배열을 만드는 기능, 숫자를 문자로 바꿔주는 기능, 특정 시간마다 이미지가 변경되도록 만들 떄 타이머 함수 기능
- **자바스크립트 코어 라이브러리 예**
  - alert()
  - document.write()

<br>

> **2) 사용자 정의 함수**

- 사용자가 필요로 해서 만든 함수

<br>

---

<br>

## :pencil:_Lesson 02. 초보자를 위한 클래스_

### _01. 클래스란?_