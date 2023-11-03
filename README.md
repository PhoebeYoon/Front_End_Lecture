##### 🍑  Front_End 과정 1단계 


## @supports
주어진 하나 이상의 CSS 기능을 웹브라우저가 지원하는 지에 따른 스타일 선언을 할 수 있도록 해준다.   
@supports 규칙은 기능 쿼리(feature query)라고 부른다. 스타일의 최상위 단계, 또는 다른 조건부 그룹 규칙에 중첩해 위치할 수 있다. 또한 조건의 논리(and, or, not) 조합도 가능하다.

아래의 예제는 display 속성의 flex 값을 지원하는 경우에  플렉스 레이아웃 처리를 시도한다.   
```html
<div class="container">
        <div>A</div>
        <div>B</div>
        <div>C</div>
    </div>
    <style>
        @supports (display: flex) {
    .container {
    	display: flex;   
        gap: 10px;
    }
    .container > div {
        flex-basis: 100px;
        background-color: #EAEAEA;
    }
}
    </style>
```

```html
<form>
        <p>Click on the text box and choose any option suggested by your browser.</p>
        <input type="text" name="name" />
        <input type="email" name="email" />
    </form>
    <style>
        input:focus-visible {
            outline: none;
        }
        @supports selector(input:autofill) {
            input:autofill {
                border: 1px solid orange;   
            }
        }
    </style>
```

출처 : http://www.devdic.com/css/reference/cssrules/css-rule:1375/@supports
