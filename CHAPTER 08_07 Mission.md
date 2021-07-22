# _CHAPTER 08 Mission_ 

<br>

## :name_badge:_Lesson 07. 미션_

#### :ballot_box_with_check:_미션 01)_ 구구단 출력을 함수로 만들기

- 풀이 전 코드는 2단에서 9단을 출력하는 99단 소스 코드이다.
- 이 코드를 print99dan이라는 함수를 만들어 포장하시오.

:ballot_box_with_check: **풀이 전 코드 : 소스**

```javascript
for(var i=2; i<=9; i++){
    document.write(i+"단 출력", "<br>");
    for(var m=1; m<=9; m++){
        document.write(i+"*"+m+"="+(i*m),"<br>");
    }
    document.write("<br>");
}
```

:ballot_box_with_check: **풀이 코드 : 소스**

```javascript
function print99dan(){
    for(var i=2; i<=9; i++){
        document.write(i+"단 출력", "<br>");
        for(var m=1; m<=9; m++){
            document.write(i+"*"+m+"="+(i*m),"<br>");
        }
        document.write("<br>");
    }    
}
print99dan();
```

##### :pencil: 설명

- 먼저 구구단 구현 코드를 포장할 텅빈 함수를 만든 후 기존 코드를 함수 내부로 이동시켜준다.
- 마지막으로 함수 호출만 해주면 끝

<br>

----

<br>

#### :ballot_box_with_check:_미션 02)_ 사칙연산 계산기 만들기1

- 실행 예시처럼 동작할 수 있게 사칙연산 처리를 전문으로 하는 함수를 만들어라.

<br>

##### :pencil: 실행 예

```javascript
document.write("1 결과 = " + calculator("+", 20, 10), "<br>");
document.write("2 결과 = " + calculator("-", 20, 10), "<br>");
document.write("3 결과 = " + calculator("*", 20, 10), "<br>");
document.write("4 결과 = " + calculator("/", 20, 10), "<br>");
document.write("5 결과 = " + calculator("%", 20, 10), "<br>");
```

##### :pencil: 실행 결과

```javascript
1 결과 = 30
2 결과 = 16
3 결과 = 200
4 결과 = 2
5 결과 = 지원하지 않는 연산자입니다.
```

<br>

##### :computer: 풀이 : 소스

```javascript
function calculator(op, num1, num2){
    var result="";
    
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
            result = "지원하지 않는 연산자 입니다."            
    }
    return result;
}
document.write("1 결과 = " + calculator("+", 20, 10), "<br>");
document.write("2 결과 = " + calculator("-", 20, 10), "<br>");
document.write("3 결과 = " + calculator("*", 20, 10), "<br>");
document.write("4 결과 = " + calculator("/", 20, 10), "<br>");
document.write("5 결과 = " + calculator("%", 20, 10), "<br>");
```

```
1 결과 = 30
2 결과 = 10
3 결과 = 200
4 결과 = 2
5 결과 = 지원하지 않는 연산자 입니다.
```

<br>

----

<br>

#### :ballot_box_with_check:_미션 03)_ 사칙연산 계산기 만들기2

- 미션02에서 만든 사칙연산 계산기에서 사칙연산 부분까지 함수로 만들어 다음과 같이 좀더 손 쉽게 사칙 연산을 할 수 있도록 만들어라.

<br>

##### :pencil: 실행 예

```javascript
document.write("더하기 = "+ calculator("+", 20, 10),"<br>");
document.write("더하기 = "+ add(20, 10),"<br>");
document.write("빼　기 = "+ sub(20, 10),"<br>");
document.write("곱하기 = "+ mul(20, 10),"<br>");
document.write("나누기 = "+ div(20, 10),"<br>");
```

<br>

##### :computer: 풀이 : 소스

```javascript
function calculator(op, num1, num2){
    var result="";
    
    switch(op){	//--------------(※5)
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
            result = "지원하지 않는 연산자 입니다."            
    }
    return result;
}
function add(num1, num2){	//--------------(※1)
    return num1+num2;
}
function sub(num1, num2){	//--------------(※2)
    return num1-num2;
}
function mul(num1, num2){	//--------------(※3)
    return num1*num2;
}
function div(num1, num2){	//--------------(※4)
    return num1/num2;
}

document.write("더하기 = "+ calculator("+", 20, 10),"<br>");	//-----------(※6)
document.write("더하기 = "+ add(20, 10),"<br>");
document.write("빼　기 = "+ sub(20, 10),"<br>");
document.write("곱하기 = "+ mul(20, 10),"<br>");
document.write("나누기 = "+ div(20, 10),"<br>");
```

```
더하기 = 30
더하기 = 30
빼　기 = 10
곱하기 = 200
나누기 = 2
```

<br>

##### :pencil: 설명

- `(※1)`,`(※2)`, `(※3)`, `(※4)` 먼저 신규로 함수를 추가해 각각의 함수에 더하기, 뺴기, 곱하기, 나누기 기능을 구현해 준다.
- `(※5)` switch 구문에 작성된 사칙연산 기능을 하는 구문 대신 신규로 작성한 함수를 호출해 준다.
- `(※6)` 신규로 등록한 사칙연산 함수가 정상적으로 동작하는지 확인하기 위한 코드를 추가

<br>

----

<br>

#### :ballot_box_with_check:_미션 04)_ 심플 갤러리 함수로 만들기1

- 심플 갤러리를 실행 예처럼 동작하게 simpleGallery() 함수 버전으로 만드는 것
- 기존 코드를 활용해 지금부터 simpleGallery()를 완성하시오.

<br>

##### :pencil: 실행 예

```javascript
simpleGallery(5,150,150);
```

<br>

##### :pencil: 실행 결과











