# _CHAPTER 07 Mission_ 

<br>

## :name_badge:_Lesson 06. 미션_

#### :ballot_box_with_check:_미션 01)_ for문을 while문으로 변경하기

- 3단을 출력하는 예제이다. for문 대신 while문으로 풀어라

:ballot_box_with_check: **풀이 전 코드 : 소스**

```javascript
var dan=3;
for(var i=1; i<=9; i++){
    document.write(dan+"*"+i+"="+(dan*i)+"<br>");
}
```

:ballot_box_with_check: **풀이 코드 : 소스**

```javascript
var dan=3;
var i=1;
while(i<=9){
    document.write(dan+"*"+i+"="+(dan*i)+"<br>");
    i++;
}
```

##### :pencil: 설명

- for문 대신 while문을 사용하려면 앞에서 알아본 것처럼 다음과 같이 구문에 맞춰 사용한다.

```javascript
초깃값;
while(조건식){
    증감;
}
```

<br>

#### :ballot_box_with_check:_미션 02)_ 입력값 합 구하기

- end가 입력될 떄까지 숫자를 계속해서 입력받아 다음과 같이 출력되게 만들어라.

##### :pencil: 요구사항

- `window.prompt()` 를 이용해 값을 입력받을 때 횟수가 출력되어야 한다.
- 입력값이 end면 `alert()`를 이용해 "입력이 종료 되었습니다." 메시지를 띄운 후 프로그램 종료
- end가 아닌 경우 입력받은 값의 합을 `document.write()`를 이요해 화면에 출력

:ballot_box_with_check: **풀이 코드 : 소스**

```javascript
var result=0;
var i=1;
while(true){
    var value=window.prompt(i+" 번째 입력 ");
    if(value=="end"){
        alert("입력이 종료 되었습니다.");
        break;
    }
    
    result+=parseInt(value);
    document.write("현재 합은 = " + result, "<br>");
    i++;
}
```

##### :pencil: 설명

- 반복 횟수가 정해져 있지 않다면 for문 대신 while문이 적합하다.
- 주의해야 할 구문은 입력값이 숫자로된 문자열이기 때문에 정수 연산을 위해
  - paresInt() 또는 Number()의 기능을 이용해 문자를 숫자로 형변환 해야한다.



