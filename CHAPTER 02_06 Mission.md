# _CHAPTER 02 Mission_ 



## :name_badge:_Lesson 06. 미션_

#### :ballot_box_with_check:_미션 01)_ 문자열 연산자 활용하기

- 이름을 각각 한 글자씩 나누어 변수에 담은 후 이 내용을 다시 하나의 변수에 담아 화면에 출력해 보시오.

```javascript
var name1="오";
var name2="태";
var name3="권";
var name=name1+name2+name3;
document.write(name);
```

<br>

#### :ballot_box_with_check:_미션 02)_ 복합 연산자 활용하기

- 복합 연산자를 이용해 풀이 전 코드를 간단하게 표현해 보시오.

```javascript
// 풀이 전
var a = 10;
a=a+20;
document.write("a = " +a);

// 풀이 후
var a = 10;
a+=20
document.write("a = " +a);
```

<br>

#### :ballot_box_with_check:_미션 03)_ 증감 연산자 활용하기

- 증감연산자를 이용하여 풀이 전 코드를 간단하게 표현해 보아라

```javascript
// 풀이 전
var a=10;
a=a+1;
document.write("a =" +a);


// 풀이 후
var a=10;
a++;
document.write("a =" +a);

//또는
var a=10;
++a;
document.write("a =" +a);
```

- 미션03의 경우 연산 결과값을 다른 변수에 저장하지 않기 때문에 전위 연산자와 후위 연산자 둘 중 아무거나 사용해도 된다.

<br>

#### :ballot_box_with_check:_미션 04)_ 전위 연산자 테스트

- 다음 코드가 실핼되면 변수 a, b에는 어떤 값이 저장될까?

```javascript
var a=10;
var b=++a;
document.write("a ="+a, "b="+b);
```

- 풀이
  - a = 11 b=11
- 설명
  - 증감연산자에서 배운 것처럼 var b=++a는 다음과 같다.

```javascript
a=a+1;
var b=a;

// a=11, b=11이 된다.
```

<br>

#### :ballot_box_with_check:_미션 05)_ 후의 연산자 테스트

- 다음 코드가 실행되면 변수 a, b에는 어떤 값이 저장될까?

```javascript
var a = 10;
var b = a++;
document.write("a =" + a, "b =" + b);
```

- 풀이
  - a=11, b=10
- 설명
  - var b=a++는 다음과 동일하다

```javascript
var b=a;
a=a+1;
// a=11, b=10이 된다.
```

<br>