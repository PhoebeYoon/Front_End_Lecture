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


### 6.함수같은 클래스

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




