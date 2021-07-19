# _CHAPTER 05 Mission_ 



## :name_badge:_Lesson 03. 미션_

#### :ballot_box_with_check:_미션 01)_ switch를 활용한 간단한 계산기 만들기

- switch문을 활용해 두 개의 수와 하나의 사칙연산자를 입력받아 계산 결과값을 출력하는 간단한 계산기를 만들어라.

```javascript
var num1 = window.prompt("첫 번째 숫자 값을 입력해 주세요.");
var op = window.prompt("사칙 연사자 중 하나를 입력해 주세요.");
var num2 = window.prompt("두 번째 숫자 값을 입력해 주세요.");

// 문자를 숫자로 형변환
num1 = parseInt(num1);
num2 = parseInt(num2);

switch(op){
    case "+" :
        result = num1 + num2;
        break;
    case "-" :
        result = num1 - num2;
        break;
    case "*" :
        result = num1*num2;
        break;
    case "/" :
        result = num1/num2;
        break;
    default :
        result = "지원하지 않은 연산자입니다.";
}

alert(num1 + op + num2 + "=" + result);
```

- 설명
  - 계산기는 가장 대표적인 switch 예제 중 하나이다.
  - 비교 대상이 특정 값과 같은 경우 if보다는 switch가 적합하다.

<br>

#### :ballot_box_with_check:_미션 02)_ 랜덤 경품 추첨기

- 이번 미션은 앞에서 풀었던 경품 추첨기를 업그레이드한 내용이다.
- 추첨 버튼을 클릭할 때마다 1에서 10까지의 숫자를 랜덤하게 뽑아(생성), 다음 요구사항에 맞게 출a력하시오

:paperclip: ***요구사항***

1. 3번이면 당첨! 냉장고
2. 5번이면 당첨! 세탁기
3. 8번이면 당첨! TV
4. 이외의 번호면 꽝!

:white_check_mark: **풀이 전 코드 : 소스** 

```javascript
$(document).ready(function(){
    // 버튼에 클릭 이벤트 리스너 등록
    $("#start").click(function(){
        // 여기에 소스를 입력해 주세요.
    }
}
```

<br>

:white_check_mark: **풀이 : 소스** 

```javascript
$(document).ready(function(){
    // 버튼에 클릭 이벤트 리스너 등록
    $("#start").click(function(){
        // 여기에 소스를 입력해 주세요.
        
        var luckyValue = parseInt(Math.random()*10)+1; //----------(※1)
        
        switch(luckyValue){ //----------(※2)
            case 3 : 
                alert("냉장고");
                break;
            case 5 :
                alert("당첨! 세탁기");
                break;
            case 8 :
                alert("당첨! TV");
                break;
            default : 
                alert("꽝!");            
        }
    })
})
```

- `※1`에서의 **Math.random** 이 함수는 1 사이의 랜덤 숫자를 발생하는 기능으로서 여기에 10을 곱하면 0에서 9 사이의 랜덤 숫자를 구할 수 있다. 
  - 대신 값이 정수가 아닌 소수로 나오기 떄문에 `parserInt()`를 이용해 정수로 형변환한다.
- `※2` 앞에서 만든 랜덤 숫자를 switch문의 조건식에 넣어 정해진 번호에 맞게 경품을 출력해준다.

<br>

#### :ballot_box_with_check:_미션 03)_ switch를 활용한 물고기 움직이기

- 증감연산자를 이용하여 풀이 전 코드를 간단하게 표현해 보아라

:paperclip: ***요구사항***

1. 초기 시작 위치 : x(left) = 50, y(top) = 200
2. 왼쪽 화살표 버튼을 누르는 경우 왼쪽으로 -50만큼 이동
3. 오른쪽 화살표 버튼을 누르는 경우 오른쪽으로 +50만큼 이동
4. 위쪽 화살표 버튼을 누르는 경우 위쪽 -50만큼 이동
5. 아래쪽 화살표 버튼을 누루는 경우 아래쪽 +50만큼 이동
6. 단, 물고기가 움직이는 영역(#panel) 밖으로 넘어가면 안됨.

