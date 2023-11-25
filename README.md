##### 🍑  Front_End 과정 1단계 

### 🗒️  SASS 
CSS의 단점을 보완하기 위해 만든 CSS 전처리기이다. 보통 CSS를 사용하다보면 단순 반복되는 부분이 많은 등, 불편함이 느껴지기 마련인데, SASS는 이 부분을 거의 완전히 해소시켜주는 스타일시트 언어다. SASS에는 Sass와 SCSS가 있다.   
또한 CSS의 확장팩 같은 언어이기 때문에 CSS 파일 그 자체를 SCSS로 확장자만 바꾸어주어도 정상적으로 작동한다. 다만 SASS 자체는 개발자용 언어이기 때문에 웹브라우저가 읽을 수 없다. 따라서 중간에 컴파일러를 거쳐서 CSS로 변환하여 HTML에 연결한다.

비슷한 CSS 전처리기 언어로는 LESS, Stylus 등이 있다. 

출처 : https://namu.wiki/w/Sass  

### 🗒️ 사용법 
node.js 가 설치되어 있다면 터미널창에서
```
>sudo npm install -g node-sass  (Mac)
>npm install -g node-sass (window)
[sass 버전 알아보기 ]
>sudo npm show sass version
```
### 🗒️ Sass 를 css 로 번역하는 사이트  
https://www.sassmeister.com/    
https://css2sass.herokuapp.com/    

### 🗒️ 사용방법  

index.html  ```( <link rel="stylesheet" href="/css/style.css"> 추가)```    
\style (빈폴더)   
\scss\style.scss  와 같이 구조를 만들고 style.scss에 스타일을 넣는다.  

터미널에 이렇게 입력한다   

```
>sudo npm i -g sass  (맥)
>sass --watch scss/style.scss  css/style.css
```
아래 이미지같은 결과가 만들어진다.   
<img width="192" alt="스크린샷 2023-11-25 오후 4 50 36" src="https://github.com/PhoebeYoon/WhatKindOfLikeThis/assets/48478079/37c60517-7e25-4bfb-a7a5-cf998bfe047c">

**확장프로그램을 설치해서 사용할 수도 있다.**    
확장프로그램을 설치하면 위에서처럼 터미널에서 해줄 필요가 없다.    
<img width="551" alt="스크린샷 2023-11-25 오후 4 59 38" src="https://github.com/PhoebeYoon/WhatKindOfLikeThis/assets/48478079/7ce64feb-1f4a-42dc-9d48-9b18735f8945">

vscode> 설정 > 검색어 : live scss > ~ complier , Config 두개의 내용이 검색된다.    
config로 검색된 내용을 살펴보면 **'settings.json에서 편집'** 보인다. 이곳을 클릭해서 **settings.json** 파일 내용을 연다.    
내용중에 **'liveSass ~~ '** 부분을 찾은 다음에   
**"liveSassCompile.settings.formats"** 있는지 확인한다.     
만약 없다면 내용을 입력한다. 앞부분을 입력하면 자동완성으로 나머지 내용이 삽입된다.   
그곳에 **"savePath" :"/css"**  ( null 로 되어 있다면 ) 적어준다.   
또한,  **"format": "expanded"** 로 되어 있다면 압축된 형태가 아닌 일반형태이며   
 **"format": "compressed"** 는 압축된 형태로 컴파일된다.   

그러면 컴파일해서 \css폴더에 넣어주도록 만든다.   







### 🗒️ 비교

1. SCSS
Sassy CSS, 가장 큰 특징은 기존 Sass의 문법에서, CSS의 원래 문법에서 사용되는 중괄호를 사용하여 CSS만 알던 사람들이 처음 접해도 직관적으로 의미를 이해할 수가 있다. 
2. 비교
[css]
```css
ul {
    list-style:none;
    width:1000px;
    margin:0 auto
    }
ul li {
    float:left;
    }
ul li a {
     color:black;
     padding:20px;
     display:block;
    }

```
[sass]   
```
ul {
    list-style:none;
    width:1000px;
    margin:0 auto;
    li {
        float:left;
        a {
            color:black;
            padding:20px;
            display:block;
        }
    }
}
```  

### 🗒️ SASS 의 기능
**네스팅** - 계층적으로 상속되는 CSS를 더욱 계층적으로 보이게 만드는 기능이다. 선택자에서 상위 계층을 적던 것을 정리하고 관련 요소들을 그룹으로 묶을 수 있게 되어 더욱 깔끔해진다.

### 🗒️ SassScript
1. 변수 - $를 사용하여 변수를 지정한다. 중복된 단어를 변수로 치환하여 유지 보수가 쉬워진다.
[css]
```
.dv1 {width:1000px;margin:0 auto;border:1px solid black}
.dv2 {width:200px;border:1px solid black}
.dv3 {width:500px;float:left;border:1px solid black}
.dv4 {width:700px;position:relative;border:1px solid black}
.dv5 {width:100px;position:absolute;border:1px solid black}
```

[sass]  
```
$bLine:1px solid black; /* 여기만 바꾸면 5개의 클래스 값을 전부 바꿀 수 있다.  */
 
.dv1 {width:1000px;margin:0 auto;border:$bLine}
.dv2 {width:200px;border:$bLine}
.dv3 {width:500px;float:left;border:$bLine}
.dv4 {width:700px;position:relative;border:$bLine}
.dv5 {width:100px;position:absolute;border:$bLine}
```

2. 연산 - 값 대신 표현식을 지정할 수 있다. 값의 맥락을 명시할 때에 사용할 수 있다. 다만 상대값(% - px, vh - px 등)을 연산할 수는 없으므로 CSS에서 지원하는 calc() 함수를 써야 하며, 나눗셈의 / 기호 역시 CSS에서 grid-area 속성 등에서 사용하고 있기 때문에 나눗셈을 할 때에도 calc() 함수를 써야 한다. 다만 나눗셈에 쓰이는 calc()는 CSS가 아닌 SASS에서 따로 사용하는 함수이다.
[css]
```
.dv1 {float:left;width:101.11111px;margin-right:10px}
```

[sass]  
```
.dv1 {float:left;width:calc(1000px / 9) - 10;margin-right:10px}
```

3. 함수 - 동일한 기능을 가진 코드를 그룹화하여 중복을 제거하거나 기능을 명시하여 유지관리에 도움을 준다. mixin과 function이 있는데, 하는 일이 좀 다르다.
@mixin: 함수 안에 들어 있는 구문으로 대체해 준다. 어떻게 보면 문자열 변수와 비슷한 기능을 한다고 볼 수 있다. 불러 쓸 때는 앞에 @include를 붙인다.
@function: 함수 안에 있는 구문으로 계산을 한 뒤, @return 명령어로 특정한 값을 내보낸다. 프로그래밍 언어의 function과 같은 기능을 한다. 불러 쓸 때는 함수명만 쓰면 된다.

[css]
```
.dv1 {width:1000px;border:1px solid black;position:absolute;left:50%;top:50%;transform:translate(-50%,-50%)}
.dv2 {width:200px;border:1px solid black;position:absolute;left:50%;top:50%;transform:translate(-50%,-50%)}
.dv3 {width:500px;border:1px solid black;position:absolute;left:50%;top:50%;transform:translate(-50%,-50%)}
.dv4 {width:700px;border:1px solid black;position:absolute;left:50%;top:50%;transform:translate(-50%,-50%)}
.dv5 {width:100px;position:absolute;border:1px solid black;position:absolute;left:50%;top:50%;transform:translate(-50%,-50%)}
```

[sass]  
```
@mixin centering(){
  position:absolute;left:50%;top:50%;transform:translate(-50%,-50%)
}

.dv1 {width:1000px;@include centering()}
.dv2 {width:200px;@include centering()}
.dv3 {width:500px;@include centering()}
.dv4 {width:700px;@include centering()}
.dv5 {width:100px;@include centering()}
```

[css]
```
.dv1 {width:225px}
.dv2 {width:525px}
.dv3 {width:150px}
```

[sass]  
```
@function width-cal($a, $b){
  @return $a * $b;
}

.dv1 {width:width-cal(900px, 3/12)}
.dv2 {width:width-cal(900px, 7/12)}
.dv3 {width:width-cal(900px, 2/12)}
```




4. 반복문 - 비슷한 구문의 반복 작성을 편하게 할 수 있다.
[css] 
```
div:nth-child(1) {
  top: 10px;
}
div:nth-child(2) {
  top: 20px;
}
div:nth-child(3) {
  top: 30px;
}

…

div:nth-child(60) {
  top: 600px;
}
```
[sass]   
```
@for $i from 1 through 60 {
    div:nth-child(#{$i}){
        top:10px * $i;
    }
}
```



5. 조건문 - 조건에 따라 속성의 값을 다르게 할 수 있다.

[css]
```
.container *:nth-child(1) {
  -ms-grid-row: 1;
  -ms-grid-column: 1;
  grid-area: 1/1;
}

.container *:nth-child(2) {
  -ms-grid-row: 1;
  -ms-grid-column: 2;
  grid-area: 1/2;
}

.container *:nth-child(3) {
  -ms-grid-row: 1;
  -ms-grid-column: 3;
  grid-area: 1/3;
}

.container *:nth-child(4) {
  -ms-grid-row: 1;
  -ms-grid-column: 4;
  grid-area: 1/4;
}

.container *:nth-child(5) {
  -ms-grid-row: 2;
  -ms-grid-column: 1;
  grid-area: 2/1;
}

…

.container *:nth-child(60) {
  -ms-grid-row: 15;
  -ms-grid-column: 4;
  grid-area: 15/4;
}
```
[sass]   
```
.container{
    *{
      @for $i from 1 through 60 { 
        &:nth-child(#{$i}){ /* #{}는 숫자를 문자로 변환해준다. 또한 &는 부모를 선택하게 하는 선택자이다. */
          @if ($i%4 == 0) {
            grid-area:#{calc($i / 4)} / 4;
          }
          @else {
            grid-area:#{floor(calc($i / 4)) + 1} / #{$i % 4};
          }
        }
      }
    }
  }
```

참조 : https://www.youtube.com/watch?v=nu5mdN2JIwM (실습파일)    


