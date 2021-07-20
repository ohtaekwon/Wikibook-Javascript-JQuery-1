# _CHAPTER 06 - 반복문for_

<br>

## :speaker: INTRO

<br>

:pushpin:***조건문과 반복문***

- for
- while

<br>

## :information_source:INDEX

|     Lesson      |              Content               |
| :-------------: | :--------------------------------: |
| ***Lesson 01*** |          **반복문 소개**           |
| ***Lesson 02*** |           **for문 소개**           |
| ***Lesson 03*** |           **단일 for문**           |
| ***Lesson 04*** | **for문에서 continue문과 break문** |
| ***Lesson 05*** |           **다중 for문**           |
| ***Lesson 06*** |              **미션**              |

<br>

---

<br>

## :pencil:_Lesson 01. 반복문 소개_

### _01. 반복문이란?_

- 반복문은 특정 구문을 여러 번 반복해서 실행할 때 사용하는 자바스크립트 제어문이다.

- 반복문을 사용하면 특정 구문을 여러 번 작성하지 않고 `재사용`(및 중복제거)을 할 수 있다.

<br>

### _02. 반복문은 이럴 때 사용_

> 1) 반복문을 사용하지 않은 경우

**질문 01) ** 당신의 이름을 화면에 출력해부시오.

```javascript
document.write("OHTAEKWON");
```

<br>

**질문 02) ** 당신의 이름을 화면에 10번 출력해부시오.

```javascript
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
```

<br>

**질문 03) ** 당신의 이름을 화면에 1000번 출력해 보시오..

- 반복구문(for)을 사용하지 않으면 힘들다.

<br>

> 2) 반복문을 사용하는 경우

**질문 01) ** 당신의 이름을 화면에 10번 출력해 보시오.

```javascript
// 반복문을 사용하기 전
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");
document.write("1. OHTAEKWON<br>");


// 반복문을 사용 후
for(var i=1; i<=10; i++)
    document.write(i+". OHTAEKOWN<br>");
```

<br>

**질문 02) ** 여러분의 이름을 화면에 1000번 출력해 보시오.

```javascript
for(var i=1; i<=1000; i++)
    document.write(i+". OHTAEKOWN<br>");
```

<br>

**질문 03) ** 당신의 이름을 500번만 찍 돼 앞 번호를 홀수만 찍히도록 하시오.

```javascript
for(var i=1; i<=1000; i+=2) // 1부터 시작하고 2씩 더해진다면 '홀수'만 나타나게 된다.
    document.write(i+". OHTAEKOWN<br>");
```

<br>

### _03.  반복문의 종류_

- 자바스크립트에서 제공하는 반복문은 `for`와 `while` 두 가지가 있다.

| 종류  | 설명                                                         |
| ----- | ------------------------------------------------------------ |
| for   | 가장 일반적으로 사용하는 반복문이다. <br />**반복횟수가 정해진 경우** 주로 사용한다. |
| while | for로 만들어진 반복문을 비교적 간결하게 처리할 수 있는 반복문이다. <br />**무한 반복하는 경우** 주로 사용한다. |

<br>

---

<br>

## :pencil:_Lesson 02. for문 소개_

### _01. for문이란?_

- for문은 특정 구문을 여러 번 반복하고 싶을 때 사용하는 반복문이다.
- ***반복 횟수가 정해진 경우 주로 사용***

<br>

### _02. for문은 이럴 때 사용_

- 당신이 많이 사용하는 게시판의 게시물 목록을 출력할 때 for문을 사용
- 공지사항 목록을 출력할 때 for문을 사용
- 구글 지도에 정보를 출력할 때 for문을 사용
- 메뉴를 만들 때, 메뉴 항목을 출력할 때 for문을 사용
- 갤러리를 만들 때, 이미지 목록을 출력할 때도 for문을 사용

<br>

### _03. for문 종류_

##### ***1) 단일 for문***

- 가장 일반적인 for문.
- for문이 오직 하나인 경우

```javascript
for(초깃값; 조건식; 증감){
    실행구문;
    . . . . .
}
```

<br>

##### ***2) 다중 for문***

- - 다중 for문은 for문 안에 또다른 for문이 들어있는 구조를 다중 for문이라고 부른다.

```javascript
for(초깃값; 조건식; 증감){
    실행구문;
    . . . . 
    for(초깃값; 조건식; 증감){
        . . . . 
    }
}
```

***진행 순서는 먼저 단일 for문을 알아보며 단일 for문을 이해한다면 다중 for문도 어렵지 않게 이해할 수 있다.***

<br>

---

<br>

## :pencil:_Lesson 03. 단일 for문_

### _01. 사용법_

```javascript
// 1. 반복 구문이 한 문장일 때는 {} 생략해도 된다/
for(초깃값; 조건식; 증감)
    실행구문;

// 2. 반복 구문이 여러 문장일 때는 {}로 감싸준다.
for(초깃값; 조건식; 증감){
    실행구문1;
    실행구문2;
    for(초깃값; 조건식; 증감){
        .....
    }
}
```

<br>

#### :memo:_예제 01)_ for가 어떻게 실행되는지 자바스크립트 엔진이 되어 보자.

```javascript
for(var i=0; i<10; i++){
    document.write("i =" + i, "<br>");
}
document.write("종료 i= "+i);
```

```
i =0
i =1
i =2
i =3
i =4
i =5
i =6
i =7
i =8
i =9
종료 i= 10
```

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/06_03_1.png?raw=true)

>  1) 초깃값 부분 실행

- 자바스크립트에 의해 for문이 실행되면 먼저 초깃값 위치 내용인

  `var i = 0;`

  이 실행되어 i라는 변수가 만들어진다. 

  - ***여기서 초깃값은 오직 한 번만 실행되며 이 후로는 실행되지 않는다.***

<br>

>  2) 조건식 부분 실행

- 조건식 위치 내용이 실행되어 i<0 을 비교한다. 이때 i가 0이니 다음과 같은 조건식이 실행된다.

  `0 < 10`

  만약 이 조건이 거짓인 경우 FOR문을 빠져 나가고 참인 경우 실행구문이 실행된다.

  이때 증감 위치의 내용이 아닌 실행구문이 실행된다.

<br>

>  3) 실행구문 실행

- i < 10 의 결과값이 참이 되어 실행구문인 document.write("i = " +i) 내용이 실행된다.

  **실행 결과 : 출력 i = 0**

<br>

>  4) 증감 부분 실행

- for문의 마지막 부분이 실행되면 for 문은 위쪽으로 올라와 증감 부분을 실행한다.
- 이때, `i++`라서 `i`는 `1`이 된다.

<br>

>  5) 조건식 부분 실행

- 바로 이어서 증감 부분의 실행 결과값을 가지고 조건식을 실행한다. 

- 이때 `i`가 `1`라서 다음과 같은 조건식이 실행된다.

  `i < 10`

  조건식이 거짓이면 for문 루프를 빠져 나가고 참이면 실행구문은 실행된다.

<br>

>  6) 실행구문 실행

- 실행 내용은 3번과 같으며 조건식 거짓일 때까지 4번에서 6번 내용이 계속해서 반복 실행된다.

|   단계   |     초깃값     |          조건식           |     실행구문     |      증감      | i값  |
| :------: | :------------: | :-----------------------: | :--------------: | :------------: | :--: |
| **1번**  | 실행1(var i=0) |  실행2 (0<10), ***참***   | 실행3 (i값 출력) |       X        |  O   |
| **2번**  |       X        |  실행2 (1<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=0→1)  |  1   |
| **3번**  |       X        |  실행2 (2<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=1→2)  |  2   |
| **4번**  |       X        |  실행2 (3<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=2→3)  |  3   |
| **5번**  |       X        |  실행2 (4<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=3→4)  |  4   |
| **6번**  |       X        |  실행2 (5<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=4→5)  |  5   |
| **7번**  |       X        |  실행2 (6<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=5→6)  |  6   |
| **8번**  |       X        |  실행2 (7<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=6→7)  |  7   |
| **9번**  |       X        |  실행2 (8<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=7→8)  |  8   |
| **10번** |       X        |  실행2 (9<10), ***참***   | 실행3 (i값 출력) | 실행4 (i=8→9)  |  9   |
| **11번** |       X        | 실행2 (10<10), ***거짓*** |        X         | 실행4 (i=9→10) |  10  |

- 초깃값은 오직 한번만 실행되며,
  - 조건식은 11번
  - 증감은 10번
  - 실행구문 10번

<br>

>  7) 루프 탈출

- 자바스크립트 엔진은 for문의 조건식의 결과값이 거짓이 되는 경우 for를 멈추고 for 다음 구문의 내용을 실행한다
- 최종 i값 10이 출력된다.

- 최종 결과
  - i =0
    i =1
    i =2
    i =3
    i =4
    i =5
    i =6
    i =7
    i =8
    i =9
    종료 i= 10

<br>

### _02. 예제_

#### :memo:_예제 02)_ 풀이 전 코드를 for문을 이용해 변경하여라

:ballot_box_with_check: **풀이 전 코드 : 소스**

```javascript
document.write("1<br>");
document.write("2<br>");
document.write("3<br>");
document.write("4<br>");
document.write("5<br>");
document.write("6<br>");
document.write("7<br>");
document.write("8<br>");
document.write("9<br>");
document.write("10<br>");

```

:one: **풀이 01: 소스**

```javascript
for(var i=0; i<10; i++)
    document.write((i+1)+"<br>");
```

```
1
2
3
4
5
6
7
8
9
10
```

<br>

:two: **풀이 02: 소스**

```javascript
for(var i=0; i<10; i++)
    document.write(i+"<br>");
```

```
0
1
2
3
4
5
6
7
8
9
```

<br>

:three: **풀이 03: 소스**

```javascript
for(var i=100; i<110; i++)
    document.write((i-99)+"<br>");
```

```
1
2
3
4
5
6
7
8
9
10
```

<br>

:four: **풀이 04: 소스**

```javascript
for(var i=1; i<10; i+=2){
    document.write(i+"<br>");
    document.write((i+1)+"<br>");
}
```

```
1
2
3
4
5
6
7
8
9
10
```

<br>

:five: **풀이 05: 소스**

```javascript
for(var i=10; i>=1; i--){
    document.write((11-i)+"<br>");
}
```

```
1
2
3
4
5
6
7
8
9
10
```

<br>

- 메모
  - for문에서 초기 변수 이름으로 i를 많이 사용하는데 이는 **iteration**의 약자를 의미한다.

- 설명
  - for문의 핵심은 `반복 횟수`이다.
  - 초깃값과 조건식 그리고 증감 값이 어떻든 풀이 01~ 풀이 05 모두 **반복 횟수가 같다.**
  - 풀이  01의 경우 가장 일반적인 풀이 방법
    - i 가 0에서부터 10보다 작을 때까지 총 10번 반복한다. 
    - 출력시에 i에서 1을 더해서 출력한다.
  - 풀이 02는 이번 예제 풀이 방법 중에서 가장 효율적인 방법
    - i값이 1부터 시작하기 떄문에 숫자 1부터 출력하기 위해 i에 값을 더하거나 뺼 필요가 없음
  - 풀이 03, 초깃값은 0 또는 1이 아닌 어떤 값이 와도 상관이 없다.
    - 이번 미션에서 중요한 건 몇 번 반복되는 것과 1부터 출력하는 것

<br>

#### :memo:_예제 03)_ 변수 활용

- for문을 이용해서 별표 10개를 가로로 찍되, 별표를 변수에 차곡차곡 저장한 후 for문의 루프를 벗어난 후에 별표를 찍어라.
- 즉 최종적으로 다음의 실행화면이 출력되게 하여라.
  - 실행화면
    - result = `**********`

<br>

:one: **풀이 01: 소스**

```javascript
document.write("result = ");
for(var i=1; i<=10; i++){
    document.write("*");
}
// result = **********
```

<br>

:two: **풀이 02: 소스**

```javascript
var result="";
for(var i=1; i<=10; i++){
    result += "*";
}
document.write("result =" +result);

// result = **********
```

- 설명
  - 풀이 01과 풀이 02의 차이는 변수 활용에 있다.
  - 풀이 01, document.write()라는 함수를 10번 호출한 것
  - 풀이 02, 10번 반복하여 변수에 별표를 하나씩 추가한 후 document.write()를 한번 호출한 경
  - 실무에서는 01보다 02 방식을 더 많이 사용한다.

<br>

#### :memo:_예제 04)_ 배열 + for 활용

- for문을 이용해서 data 배열의 내용을 실행 결과처럼 출력하여라.
  - var data = ["변수", "연산자", "형변환", "조건문 if", "조건문 switch", "반복문 for", "반복문 while", "함수", "클래스"];

- 실행결과

  0 번째 내용 = 변수

  1 번째 내용 = 연산자

  2 번째 내용 = 형변환

  3 번째 내용 = 조건문 if

  4 번째 내용 = 조건문 switch

  5 번째 내용 = 반복문 for

  6 번째 내용 = 반복문 while

  7 번째 내용 = 함수

  8 번째 내용 = 클래스

:one: **풀이**

```javascript
var data = ["변수", "연산자", "형변환", "조건문 if", "조건문 switch", "반복문 for", "반복문 while", "함수", "클래스"];

// 여기 풀이
for(var i=0; i<data.length; i++){
    document.write(i + "번째 내용 = " + data[i], "<br>");
}
```

```
0번째 내용 = 변수
1번째 내용 = 연산자
2번째 내용 = 형변환
3번째 내용 = 조건문 if
4번째 내용 = 조건문 switch
5번째 내용 = 반복문 for
6번째 내용 = 반복문 while
7번째 내용 = 함수
8번째 내용 = 클래스
```

<br>

---

<br>

## :pencil:_Lesson 04. for문에서 continue문과 break문_

- for문과 같이 사용하는 명령어는
  - **continue문**
  - **break문**

### _01. continue문_

- continue문은 반복 실행 중 **특정 조건의 경우 실행구문을 실행하지 않고 다음 루프로 이동하게 하는 제어문**이다.

#### :memo:_예제 01)_ 다음 구문을 실행하면 화면에는 어떤 값이 출력될까?

```javascript
for(var i=1; i<=10; i++){
    continue;	//--------------(※1)
    document.write(i+"<br>");	//--------------(※2)
}
document.write("최종 i= " +i+ "<br>");	//--------------(※3)
```

- 실행결과
  - 최종 i = 11
- 설명
  - for문의 루프는 10번 실행되기 하지만, `※1`에 ***continue문***이 있기 때문에 `※2` 부분이 실행되지 않아 루프에서 화면에 출력되는건 전혀 없다.
  - 루프가 모두 끝난 후 `※3`내용이 실행돼 i값이 출력된다.

<br>

### _02. break문_

- 반복문에서 break문은 루프를 강제적으로 빠져 나오는 기능한다.
- 실행구문 중 break문을 만나면 for문은 그대로 정지되며, for루프 밖으로 빠져나가게 된다.
- 이후 밖에 있는 다음 구문을 실행하게 된다.

#### :memo:_예제 03)_ 다음 구문을 실행하면 화면에는 어떤 값이 출력될까?

```javascript
for(var i=1; i<=10; i++){
    break;	//--------------(※1)
    document.write(i+"<br>");	//--------------(※2)
}
document.write("최종 i= " +i+ "<br>");	//--------------(※3)
```

- 실행결과
  - 최종 i = 1
- 설명
  - 반복문 실행 중 continue문이 실행되면 루프를 벗어나지 않고 다음 루프를 돌지만,
  - ***break문은 바로 루프를 벗어나게 된다.***
    - 즉, 결과는 i가 1로 출력된다.

<br>

---

<br>

## :pencil:_Lesson 05. 다중 for문_

### _01. 사용법_

```javascript
for(초깃값; 조건식; 증감){
    실행구문;
    . . . .
    for(초깃값; 조건식; 증감){
        . . . .
    }
}
```

- 설명
  - 다중 for문이란 for문 안에 for문이 있는 구조를 말한다.
  - 2중 for문뿐 아니라 3중, 10중 for문도 있다.

***EX)***

```javascript
for(var i=1; i<=5; i++){
    for(var m=1; m<=5; m++){
        document.write("i = " +i +" / "+ "m = " +m, "<br>");
    }
}
```

- 첫 번째 for문의 루프가 한 번씩 실행될 때마다 두 번째 for문의 실행구문이 다섯 번씩 실행된다.

```
i = 1 / m = 1
i = 1 / m = 2
i = 1 / m = 3
i = 1 / m = 4
i = 1 / m = 5
i = 2 / m = 1
i = 2 / m = 2
i = 2 / m = 3
i = 2 / m = 4
i = 2 / m = 5
i = 3 / m = 1
i = 3 / m = 2
i = 3 / m = 3
i = 3 / m = 4
i = 3 / m = 5
i = 4 / m = 1
i = 4 / m = 2
i = 4 / m = 3
i = 4 / m = 4
i = 4 / m = 5
i = 5 / m = 1
i = 5 / m = 2
i = 5 / m = 3
i = 5 / m = 4
i = 5 / m = 5
```



<br>

### _02. 예제_

#### :memo:_예제 01)_ 발표 출력하기

- for문을 이용하여 실행화면처럼 출력하여라.

**실행화면**

```
*
**
***
****
*****
```

:one: **풀이 소스**

```javascript
for(var i=0; i<5; i++){
    var result="";
    for(var m=0; m<=i; m++){
        result+="*";
    }
    document.write(result, "<br>");
}
```

```
*
**
***
****
*****
```

- 설명
  - 별표를 찍는 행위가 5번 일어나고 행위가 한 번씩 실행될 때마다 별표 수가 증가하는 것을 알 수 있다.

<br>

> 단계 01

먼저 간단하게 for문을 이용해 별표 찍는 것을 작성해보자

```javascript
for(var i=0; i<5; i++){
    document.write("*","<br>");
}
```

<br>

> 단계 02

그럼 이제 남아 있는 문제는 반복 횟수가 한 번씩 증가할 떄마다 별표도 증가하게끔 한다.

이 작업을 위한 사전 작업을 다음처럼 해놓자.

```javascript
for(var i=0; i<5; i++){
    var count = 1;
    var result = "";
    for(var m=0; m<count; m++)
        result+="*";
    document.write(result, "<br>");
}
```

<br>

> 단계 03

- count를 다음 표에 맞게 구하는 것

| 반복횟수 | i값  | 별표수 |
| :------: | :--: | :----: |
|    1     |  0   |   1    |
|    2     |  1   |   2    |
|    3     |  2   |   3    |
|    4     |  3   |   4    |
|    5     |  4   |   5    |

- 여러가지 해결방법이 있지만, 일단 주위 값을 이용하는 것이 우선이고 없다면, 새로운 변수를 만들자
- i에 1을 더하면 우리가 원하는 별표 수를 구할 수 있다.

<br>

> 단계 04

- 기존 풀이를 살펴보면 코드 내용 중 두 번째 for문의 조건식의 `<`를 `<=` 으로 변경하고 count위치에 `i`를 직접 넣어주면 count 변수가 필요 없는 좀더 깔끔한 노드를 만들 수 있다.

```javascript
for(var i=0; i<5; i++){
    var result="";
    for(var m=0; m<=i; m++)
        result+="*";
    document.write(result, "<br>");
}
```

```
*
**
***
****
*****
```

<br>

```javascript
for(var i=0; i<5; i++){
    for(var m=0; m<=i; m++){
        document.write("i = "+i+ " / " + "m = " + m, "<br>");
    }
}
```

```
i = 0 / m = 0
i = 1 / m = 0
i = 1 / m = 1
i = 2 / m = 0
i = 2 / m = 1
i = 2 / m = 2
i = 3 / m = 0
i = 3 / m = 1
i = 3 / m = 2
i = 3 / m = 3
i = 4 / m = 0
i = 4 / m = 1
i = 4 / m = 2
i = 4 / m = 3
i = 4 / m = 4
```



#### :memo:_예제 02)_ 발표 출력하기

- for 문을 이용해 다음 실행화면처럼 출력해보아라.

**실행화면**

```
*****
****
***
**
*
```

:one: **풀이 소스**

```javascript
for(var i=5; i>0; i--){
    var result="";
    for(var m=0; m<i; m++){
        result+="*";
    }
    document.write(result, "<br>");
}
```

```
*****
****
***
**
*
```

- **설명**
  - 메인 루프의 반복 횟수는 5번
  - 반복할 때마다 별의 수는 5개를 시작으로 하나씩 감소한 개수가 출력되어야 한다.

| 반복횟수 | 별표수 |
| :------: | :----: |
|    1     |   5    |
|    2     |   4    |
|    3     |   3    |
|    4     |   2    |
|    5     |   1    |

<br>

> 단계1

```javascript
for(var i=0; i<5; i++){
    var count = 5-i;
    var result = "";
    for(var m=0; m<count; m++)
        result +="*";
    document.write(result, "<br>");
}
```

- 최대 별표 개수인 5에서 i 값을 빼면 해당 루프에서 출력해야 할 별의 수를 구할 수 있다.

```
*****
****
***
**
*
```

<br>

> 단계2

- 앞의 풀이를 다음과 같이 변경

```javascript
for(var i=5; i>0; i--){
    var result="";
    for(var m=0; m<=i; m++)
        result+="*";
    document.write(result, "<br>");
}
```

