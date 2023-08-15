##### 🍑  Front_End 과정 1단계 


### 1. 태그선택자  



### 2. id, class 선택자 



### 3. 부모 >  자식, 후손 선택자



### 4. 다중조건 선택자


태그이름#아이디 { 속성1:속성값; 속성2:속성값; }   
태그이름.클래스명 { 속성1:속성값; 속성2:속성값; }  
.클래스명#아이디 { 속성1:속성값; 속성2:속성값; }  
선택자 사이에 공백이 제거되는 경우 여러 선택자를 동시에 만족하는 태그에 스타일을 적용 할 수 있습니다  

#아이디, .클래스명{ 속성1:속성값; 속성2:속성값; } 
태그이름, .클래스명{ 속성1:속성값; 속성2:속성값; } 

쉼표 (,)를 통해  같은 속성을 공유할 수 있습니다. 


> css에서 : 와 :: 의 역사
> 역사적으로 가상클래스와 가상요소는 모두 1개의 콜론만을 사용했습니다.
> 그러다가 :: 표기법은 이 두개를 구별하기 위한 방법으로 css3에 소개되었습니다. 단일 콜론만 사용하는 것은 권장되지 않지만 브라우저는 여전히 이 2개를 모두 호환하여 표현하고 있습니다. 



### 5. 가상(pseudo) 클래스 (class) 와 가상(pseudo) 요소 (element)  
CSS에는 가상 요소(:pseudo-element)와 가상 클래스(:pseudo-class)가 있다. 

가상클래스는 엘리먼트의 특별한 **상태**를 정의하며, 이것들을 사용해서 html 문서의 수정 없이 CSS만으로 디자인적 요소를 추가할 수 있다. 

가상 엘리먼트는 엘리먼트의 **특정부분** 을 스타일할때 사용되는 것이다. 

``` 선택자:가상클래스 { property: value; }  (콜론 1개) ```

``` 선택자::가상요소 { property: value; }  (콜론 2개) ```

가상 클래스 예를들면,   
:hover : 사용자가 해당 요소에 커서를 가져다 댔을 때  
:active : 요소가 활성화 되었거나 클릭 되었을 때  
:focus : 해당 요소에 키보드 포커스가 맞춰졌을 때   
:first-child : li 중 첫번쩨 요소에 해당 CSS를 적용  
:last-child : li 중 마지막에 해당 CSS를 적용   
:nth-child(n) : li 중 n번쩨 요소에 해당 CSS를 적용   

:peach: [50가지 가상 클래스 확인](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#alphabetical_index)
 
가상요소는 예를들면,    
::first-line   
::first-letter   
::before   
::after   


:peach: [List of 가상엘리먼트](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements#alphabetical_index)

### 6.함수같은 클래스

:is()  
:not()   
:where()   
:has()   

예)
```css
span,
div { border: red 2px solid; }
또는
:is(span, div) {
  border: red 2px solid; }

위의 2개는 동일하다
```  

```css
h2:has(+ p, + ul.red) {
  font-style: italic;
}
이것은 <h2> 바로 다음태그가 <p> 또는 <ul class="red"> 일때를 말한다. 
```
:peach: 참조 
- https://www.freecodecamp.org/news/the-difference-between-pseudo-classes-and-elements-in-css/  
- https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#selector_list




```html
:not() 예제  
<style>
p:not(.irrelevant) {
  font-weight: bold;
}

p > strong,
p > b.important {
  color: crimson;
}

p > :not(strong, b.important) {
  color: darkmagenta;
}
</style>

<p>
  <b>Mars</b> is one of the most Earth-like planets. <b>Mars</b> day is almost the same as an Earth day, only
  <strong>37 minutes</strong> longer.
</p>

<p class="irrelevant">
  <b class="important">NASA</b>'s Jet <del>Momentum</del> Propulsion Laboratory is designing mission concepts to survive
  the <b>Venus</b> extreme temperatures and atmospheric pressure.
</p>

```

```html
<style>
.fancy {
  text-shadow: 2px 2px 3px gold;
}

/* <p> elements that don't have a class `.fancy` */
p:not(.fancy) {
  color: green;
}

/* Elements that are not <p> elements */
body :not(p) {
  text-decoration: underline;
}

/* Elements that are not <div>s or `.fancy` */
body :not(div):not(.fancy) {
  font-weight: bold;
}

/* Elements that are not <div>s or `.fancy` */
body :not(div, .fancy) {
  text-decoration: overline underline;
}

/* Elements inside an <h2> that aren't a <span> with a class of `.foo` */
h2 :not(span.foo) {
  color: red;
}
</style>

<p>I am a paragraph.</p>
<p class="fancy">I am so very fancy!</p>
<div>I am NOT a paragraph.</div>
<h2>
  <span class="foo">foo inside h2</span>
  <span class="bar">bar inside h2</span>
</h2>

```

:peach: https://developer.mozilla.org/en-US/docs/Web/CSS/:not  (페이지 하단)








