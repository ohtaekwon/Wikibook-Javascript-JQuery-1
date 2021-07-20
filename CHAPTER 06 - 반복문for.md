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

> ***1) 반복문을 사용하지 않은 경우***

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

> ***2) 반복문을 사용하는 경우***

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

