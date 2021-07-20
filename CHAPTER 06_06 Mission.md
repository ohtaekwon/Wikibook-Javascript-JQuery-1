# _CHAPTER 06 Mission_ 



## :name_badge:_Lesson 06. 미션_

#### :ballot_box_with_check:_미션 01)_ for문 활용하기

- 3단을 출력하는 코드이다. for문으로 간결하게 만들어라

:ballot_box_with_check: **풀이 전 코드 : 소스**

```javascript
var dan = 3;
document.write(dan+"*1="+(dan*1)+"<br>");
document.write(dan+"*2="+(dan*2)+"<br>");
document.write(dan+"*3="+(dan*3)+"<br>");
document.write(dan+"*4="+(dan*4)+"<br>");
document.write(dan+"*5="+(dan*5)+"<br>");
document.write(dan+"*6="+(dan*6)+"<br>");
document.write(dan+"*7="+(dan*7)+"<br>");
document.write(dan+"*8="+(dan*8)+"<br>");
document.write(dan+"*9="+(dan*9)+"<br>");
```

- **설명**
  - 반복문을 활요앻서 중복 코드를 처리할 수 있다.
  - 먼저, 코드에서 변경되는 부분과 변경 되지 않는 부분을 찾는다.
  - 변경되지 않은 부분은 그대로 루프의 구문으로 넣어주고
  - 변경되는 부분은 주위에 있는 변수의 도움을 받든 아니면 신규로 변수를 만들어야 하는 대상이 된다.

![](https://github.com/ohtaekwon/Wikibook-Javascript-JQuery-1/blob/master/img/06.06_1.png?raw=true)

- for 루프를 만들어 변경되지 않는 부분을 루프 안에 넣어준다.
- 반족 횟수는 아홉 번으로 해준다.

:ballot_box_with_check: **풀이 코드 : 소스**

```javascript
var dan = 3;

for(var i=0; i<=9; i++){
    document.write(dan+"*X=" +(dan*X)+"<br>");
}

/* 	여기서 변경 되는 부분을 처리해보면 원하는 수는 
	1부터 시작해 반복이 될 때마다 1씩 증가시켜야 한다.
	i가 0부터 시작하는것을 1로 변경하면
*/

var dan=3;
for(var i=1; i<=9; i++){
    document.write(dan+"*X="+(dan*X)+"<br>")
}

/*
	마지막으로 X의 위치에 i를 대신 넣는다.
*/

var dan=3;
for(var i=1; i<=9; i++){
    document.write(dan+"*"+i+"="+(dan*i)+"<br>")
}
```

<br>

#### :ballot_box_with_check:_미션 02)_ 배열의 총 합 구하기

- 배열의 총 합을 구해 화면에 출력해 보아라.

:ballot_box_with_check: **풀이 전 코드 : 소스**

```javascript
var data = [10, 20, 30, 40, 50];
```

<br>

:ballot_box_with_check: **풀이 코드 : 소스**

```javascript
var data = [10, 20, 30, 40, 50];
var result = 0;		//------(※1)
for(var i=0; i<data.length; i++){ // data.length는 5가 나온다. index는 0부터 시작하므로 <=가 아니라 <
    result+=data[i];//------(※2)
}
alert("배열의 합은 " + result +"입니다.");
```

- 설명
  - 배열의 합을 구하는 예제는 변수 활용이 핵심이다.
    - `※1` , 총합을 저장할 변수 **result**를 만든다. ***초깃값은 반드시 0으로 설정***
    - `※2`, 루프를 돌며 배열 0번째부터 마지막 번째까지 접근해 배열에 들어 있는 값을 result변수에 더한다. 
- 정리하자면 다음과 같다.

| 루프(i값) | 배열 값 | result |
| :-------: | :-----: | :----: |
|  시작 전  |    x    |   0    |
|   i = 0   |   10    |   10   |
|   i = 1   |   20    |   30   |
|   i = 2   |   30    |   60   |
|   i = 3   |   40    |  100   |
|   i = 4   |   50    |  150   |

<br>

#### :ballot_box_with_check:_미션 03)_ 이미지를 가로로 배열하기

- 버튼을 클릭하면 이미지를 요구사항에 맞게 배열하여라

**요구사항**

1. 이미지 시작위치는 left:100, top:100
2. 하나의 이미지 영역(이미지 크기와 여백 포함) 은 150*150이다.
3. 이미지를 가로로 배열해라

- 힌트_이미지 위치 설정하기

```
$대상.css({
	left:위치값,
	top:위치값,
})
```

:ballot_box_with_check: **풀이 전 코드 : 소스**

```html
<!DOCTYPE HTML>
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title></title>

    <style>
        div.image-container {
            position: relative;
        }

        div.image-container img {
            position: absolute;
            left: 0;
            top: 0;
            width: 120px;
        }
        
        #btnStart{
            padding:5px;
            margin-bottom:5px;
        }
    </style>

    <!--

    미션 03: 이미지를 가로로 배열하기
    버튼을 클릭하면 이미지를 요구사항에 맞게 배열해 주세요.

    요구사항
        01. 이미지 시작위치는 left:100, top:100 입니다.
        02. 하나의 이미지 영역(이미지 크기와 여백 포함)은 150*150입니다.
        03. 이미지를 가로로 배열해 주세요.


    힌트 :
        이미지 위치 설정하기
            $대상.css({
                left:위치값,
                top:위치값
            })

    -->
    <script type="text/javascript"  src="../../../libs/jquery-1.11.0.min.js"></script>
    <script>
        $(document).ready(function() {
            // 버튼 클릭 이벤트 실행.
            $("#btnStart").click(function() {

                // 이미지 찾기.
                var $images = $("img");

                // 이미지 개수 구하기.
                var length = $images.length;

                // 여기에 풀이를 입력해주세요.

            });
        });

    </script>
</head>

<body>
    <div>
        <button id="btnStart">
            배열시작
        </button>
    </div>
    <div class="image-container">
        <img src="banners/1.png" >
        <img src="banners/2.png" >
        <img src="banners/3.png" >
        <img src="banners/4.png" >
        <img src="banners/5.png" >
    </div>
</body>
</html>

```

<br>

:ballot_box_with_check: **풀이 코드 : 소스**

```javascript
$(document).ready(function() {
    // 버튼 클릭 이벤트 실행.
    $("#btnStart").click(function() {
        // 이미지 찾기.
        var $images = $("img");
        // 이미지 개수 구하기.
        var length = $images.length;
        
        // 여기에 풀이를 입력해주세요.
        // 이미지 배열하기
        for(var i=0; i<length; i++){
            // n번째 이미지 구하기
            var $img = $images.eq(i);
            // 위치 값 구하기
            var x = 100+(i*150);
            // 위치 설정
            $img.css({
                left:x,
                top:100
            });
        }
    });
});
```

<br>











## :name_badge:참고

### 1) .eq()

```
선택한 요소의 인덱스 번호에 해당하는 요소를 찾습니다.
```

<br>

#### 문법(Syntax)

```
$("선택자").eq("숫자");
```

<br>

#### 정의(Definition)

- 선택한 요소의 형제 중 숫자를 통해 선택합니다.
- 음수를 설정하면 끝을 기준으로 선택합니다.

 <br>

---

<br>

### 2) $.

- $는 jquery를 의미한다.
- 함수($)을 하면 jquery $.에 해당하는 함수들이 추가된다.
- $("")jquery 함수를 사용할 수 있는 변수라는 의미로 표시하기위해 붙
