##### 🍑  Front_End 과정 1단계 

## BEM (Block, Element,Modifier) 방법론
블록, 요소, 수정자 방법론(일반적으로 BEM이라고 함)은 HTML과 CSS의 클래스에 대한 인기 있는 명명 규칙입니다. 얀덱스 팀이 개발한 이 방법의 목표는 개발자들이 주어진 프로젝트에서 HTML과 CSS의 관계를 더 잘 이해할 수 있도록 돕는 것입니다.

## How it works
[block]__[element]--[modifier]   

참조 : https://sparkbox.com/foundry/bem_by_example    

```
/* Block component */
.btn {}

/* Element that depends upon the block */ 
.btn__price {}  // 하위 항목 또는 요소는 내부에 배치될 수 있으며
                // .btn__price { }와 같이 블록 이름 뒤에 두 개의 밑줄로 표시됩니다

/* Modifier that changes the style of the block */ 
.btn--orange {}  
.btn--big {} 
// 변경을 가하지 않고 해당 특정 구성 요소를 테마화하거나 스타일화할 수 있습니다.
// 이는 btn-orange와 마찬가지로 블록 이름에 두 개의 하이픈을 추가함으로써 수행됩니다.
```

[예제]

```html
   <style>
        /* Block */
.btn {
  text-decoration: none;
  background-color: white;
  color: #888;
  border-radius: 5px;
  display: inline-block;
  margin: 10px;
  font-size: 18px;
  text-transform: uppercase;
  font-weight: 600;
  padding: 10px 5px;
}

/* Element */
.btn__price {
  background-color: white;
  color: #fff;
  padding-right: 12px;
  padding-left: 12px;
  margin-right: -10px; /* realign button text padding */
  font-weight: 600;
  background-color: #333;
  opacity: .4;
  border-radius: 5px 0 0 5px;
}
/* Element */
.btn__text {
  padding: 0 10px;
  border-radius: 0 5px 5px 0;
}
/* Modifier */
.btn--big {
  font-size: 28px;
  padding: 10px;
  font-weight: 400;
}

/* Modifier */
.btn--blue {
  border-color: #0074D9;
  color: white;
  background-color: #0074D9;
}

/* Modifier */
.btn--orange {
  border-color: #FF4136;
  color: white;
  background-color: #FF4136;
}

/* Modifier */
.btn--green {
  border-color: #3D9970;
  color: white;
  background-color: #3D9970;
}
body {
  font-family: "fira-sans-2", sans-serif;
  background-color: #ccc;
}
    </style>

<a href="https://css-tricks.com" class="btn">
        <span class="btn__text">Standard button</span>
      </a>
      
      <a href="https://css-tricks.com" class="btn btn--orange btn--big">
        <span class="btn__price">$3</span>
        <span class="btn__text">Big button</span>
      </a>
      
      <a href="https://css-tricks.com" class="btn btn--blue btn--big">
        <span class="btn__price">$4</span>
        <span class="btn__text">Big button</span>
      </a>
      
      <a href="https://css-tricks.com" class="btn btn--green btn--big">
        <span class="btn__price">$9</span>
        <span class="btn__text">Big button</span>
      </a>

```

참조 : https://css-tricks.com/bem-101/
> Note: --my-color 와 --My-color는 다르게 취급됩니다

```css
.two {
 /* --my-var가 정의되지 않았을 경우 red로 표시됨   */
  color: var(--my-var, red);  
}

.three {
  /* pink if --my-var and --my-background are not defined */
  background-color: var(--my-var, var(--my-background, pink));
}

.three {
  /* 틀림: "--my-background, pink" */
  background-color: var(--my-var, --my-background, pink);
}

```

> var() 는 나중에 정의하더라고 미리 사용하는데 문제가 없다.    
참조 : https://developer.mozilla.org/en-US/docs/Web/CSS/var



### Values in JavaScript

```js
// get variable from inline style
element.style.getPropertyValue("--my-var");

// get variable from wherever
getComputedStyle(element).getPropertyValue("--my-var");

// set variable on inline style
element.style.setProperty("--my-var", jsVar + 4);

```


### 재정의해서 사용
```html
  <style>
        :root {
  --first-color: #16f;
  --second-color: #ff7;
}

#firstParagraph {
  background-color: var(--first-color);
  color: var(--second-color);
}

#secondParagraph {
  background-color: var(--second-color);
  color: var(--first-color);
}

#container {
  --first-color: #290; // #container 안에 있는 내용은 --first-color가 :root 에 있는 것을 따르지 않고
                      //여기에 정의된 것으로 적용된다
}

#thirdParagraph {
  background-color: var(--first-color);
  color: var(--second-color);
}
    </style>
<p id="firstParagraph">
        This paragraph should have a blue background and yellow text.
</p>
<p id="secondParagraph">
  This paragraph should have a yellow background and blue text.
</p>
<div id="container">
  <p id="thirdParagraph">
    This paragraph should have a green background and yellow text.
  </p>
</div>
```

## @property
@property CSS at-rule은 API의 CSS Houdini 우산의 일부입니다. 이것은 개발자가 CSS 사용자 지정 속성을 명시적으로 정의할 수 있도록 하여 속성 유형 확인 및 제한, 기본값 설정, 사용자 지정 속성이 값을 상속할 수 있는지 여부를 정의할 수 있습니다.

참조 : https://developer.mozilla.org/en-US/docs/Web/CSS/@property




