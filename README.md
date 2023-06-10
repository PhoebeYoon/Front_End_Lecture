##### 🍑  Front_End 과정 1단계 
1. scroll-behavior
2. scroll-margin   
  

앵커태그를 이용하여 스크롤할때 이동하는 모양을 지정할 수 있다.    
scroll-behavior: smooth를 주석처리하면 일반적인 앵커태그를 이용하여 이동할때처럼 동작한다.   

```html
<!DOCTYPE html>
<html>
<head>
<style>
html { scroll-behavior: smooth;}
#section1 { height: 600px; background-color: pink; }
#section2 { height: 600px; background-color: yellow; }
</style>
</head>
<body>
<h1>Smooth Scroll</h1>
<div class="main" id="section1">
  <h2>Section 1</h2>
  <a href="#section2">Section 2로 이동</a>
</div>
<div class="main" id="section2">
  <h2>Section 2</h2>
  <a href="#section1">Section 1로 이동</a>
</div>
</body>
</html>
```   
scroll-margin은 아래 4가지 속성을 포함합니다. (그리고 이것을 사용하기 위해서는 child 엘리먼트에 scroll-snap-align를 
 부모 엘리먼트에는 scroll-snap-type를 지정해야 합니다 )
  - scroll-margin-top
  - scroll-margin-bottom
  - scroll-margin-left
  - scroll-margin-right  
  
  scroll-margin: 15px 30px 60px 90px;   
  top: 15px, right에서 30px, bottom 에서 60px, 왼쪽에서 90px 
  
  ```html
<!DOCTYPE html>
<html>
<head>
<style>
#container {
  scroll-snap-type: both mandatory;
  width: 50%;
  aspect-ratio: 1/1;
  margin: 30px auto;
  background-color: #fff;
  white-space: nowrap;
  overflow-x: scroll;
  overflow-y: scroll;
  border: solid black 2px;
}
#container > div {
  display: inline-block;
  height: 85%;
  border-radius: 5%;
  aspect-ratio: 1/1;
  scroll-snap-align: end;
  scroll-margin: 0 10px 30px 0;
}

.green    { background-color: lightgreen; }
.pink     { background-color: lightpink; }
.blue     { background-color: lightblue; }
.yellow   { background-color: yellow; }
.grey     { background-color: lightgray; }
</style>
</head>
<body>

<h3>CSS scroll-margin property, at bottom and right.</h3>
<p>Scroll towards the middle of the container, let go, and see how the scroll-margin creates 30px distance from the bottom of the element to the container, and 10px distance from right side of the element to the container.</p>

<div id="container">
  <div class="green"></div>
  <div class="pink"></div>
  <div class="yellow"></div>
  <div class="blue"></div>
  <div class="grey"></div>
  <div class="pink"></div>
  <br>
  <div class="pink"></div>
  <div class="blue"></div>
  <div class="grey"></div>
  <div class="yellow"></div>
  <div class="pink"></div>
  <div class="green"></div>
  <br>
  <div class="green"></div>
  <div class="pink"></div>
  <div class="yellow"></div>
  <div class="blue"></div>
  <div class="grey"></div>
  <div class="pink"></div>
  <br>
  <div class="pink"></div>
  <div class="yellow"></div>
  <div class="blue"></div>
  <div class="grey"></div>
  <div class="pink"></div>
  <div class="green"></div>
  <br>
  <div class="grey"></div>
  <div class="blue"></div>
  <div class="yellow"></div>
  <div class="pink"></div>
  <div class="green"></div>
  <div class="pink"></div>
  <br>
  <div class="green"></div>
  <div class="pink"></div>
  <div class="blue"></div>
  <div class="yellow"></div>
  <div class="pink"></div>
  <div class="grey"></div>
</div>

</body>
</html>

```
#### The scroll-snap-type 스크롤을 중지할 때 요소가 포커스로 스냅되는 방법과 방향을 지정합니다.  
#### The scroll-snap-align 스크롤을 중지할 때 요소가 초점으로 스냅될 위치를 지정합니다.


  
  
  
  
     


