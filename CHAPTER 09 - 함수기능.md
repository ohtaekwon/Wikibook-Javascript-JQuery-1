# _CHAPTER 09 - 함수기능_

<br>

## :speaker: INTRO

<br>

## :information_source:INDEX

|     Lesson      |                     Content                     |
| :-------------: | :---------------------------------------------: |
| ***Lesson 01*** |               **함수 기능 소개**                |
| ***Lesson 02*** | **함수 기능 1: 중복코드 제거 및 코드 재사용성** |
| ***Lesson 03*** |          **함수 기능 2: 코드 그룹화**           |
| ***Lesson 04*** |                    **미 션**                    |

<br>

---

<br>

## :pencil:_Lesson 01. 함수 대표 기능 두가지_

- 함수는 다음과 같이 크게 두 가지 기능을 갖고 있다.
  1. 중복코드 제거 및 코드 재사용성
  2. 구조 나누기

<br>

## :pencil:_Lesson 02. 중복코드 제거 및 코드 재사용성_

- 함수를 사용하지 않을 때 중복코드가 발생하는 경우

*​**:white_check_mark: 2단 코드***

```javascript
var dan = 2;
for(var i=1; i<=9; i++){
    document.write(dan+" * " + i+ "=" +(dan*i),"<br>");
}
```

***:white_check_mark:  4단 코드***

```javascript
var dan = 4;
for(var i=1; i<=9; i++){
    document.write(dan+" * " + i+ "=" +(dan*i),"<br>");
}
```

*​**:white_check_mark: 7단 코드***

```javascript
var dan = 7;
for(var i=1; i<=9; i++){
    document.write(dan+" * " + i+ "=" +(dan*i),"<br>");
}
```

<br>

이때 **함수를 이용하면** ***중복코드를 없앨 뿐 아니라 코드를 재사용할 수 있어 유지보수하기 좋은 코드***를 만들 수 있다.

```javascript
function print99dan(dan){
    // 중복되는 코드를 여기에 포장시켜 준다.
    for(var i=1; i<=9; i++){
        document.write(dan+" * " + i+ "=" +(dan*i),"<br>");
    }
}
print99dan(2);
print99dan(4);
print99dan(7);
```



