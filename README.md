##### 🍑  Front_End 과정 1단계 


##  aspect-ratio
The aspect-ratio CSS 속성은 box에 대한 가로 세로비율를 설정하는 것으로 자동 크기 및 기타 레이아웃 함수 계산에 사용된다.    
상자의 기본 width / height 비율입니다. height와 '/'가 생략되면 height는 기본적으로 '1'로 계산됩니다. 상자의 크기는 box-sizing에 의해 지정된 수치로 작동합니다.  

```html
<style>
div {
  background-color: red;
  width: 120px;
  aspect-ratio: 3/2;
}
</style>
<div>Hello</div>
<p>Aspect ratio is width/height.</p> 
```   
가로 세로의 비율은 3/2이고 width가 100px 일때 height의 비율은 width의 3/2만큼 지정됩니다 (그러니까 height는 80px로 계산된다는 말이죠)


```html

<!DOCTYPE html>
<html>
<head>
<style>

#div1 {
  position: relative;
  box-sizing: border-box;
  margin: auto;
  height: 150px;
  width: 200px;
  padding: 10px;
  border: 1px solid black;
}
#div2 {
  padding: 40px;
  box-sizing: border-box;
  position: absolute;
  border: 1px solid black;
  background-color: red;
  /* aspect-ratio:auto; */
  /* aspect-ratio: 5/2;  */
  /* aspect-ratio:1/1; */
  /* aspect-ratio:16/9; */
  aspect-ratio:0.5;
}
</style>
</head>
<body>
<h1>The aspect-ratio Property</h1>
<div id="div1">DIV1
  <div id="div2">DIV2</div>
</div>

</body>
</html>

```
