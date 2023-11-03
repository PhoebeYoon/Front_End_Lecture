##### 🍑  Front_End 과정 1단계 


## @container  
viewport가 아닌 특정 요소의 크기에 따라 스타일링을 할 수 있는 container 쿼리이다.
컨테이너 컨텍스트에 스타일을 적용하는 조건부 그룹 규칙이다.  
스타일 선언은 조건에 따라 필터링되고 조건이 true이면 컨테이너에 적용된다. 조건은 컨테이너 크기가 변경될 때 평가된다.  
스타일 선언은 해당 컨테이너의 컨텍스트에서만 유효하다. 즉, 컨테이너의 하위 요소들에게만 유효하다   

형식  
```
@container [ <container-name> ]? <container-condition> { <stylesheet> }
```

[예제] 

```html
  <style>
  .parent {
  container-type: inline-size;
  container-name: child-style;
  border: 3px solid gray;
  width: 200px;
  height: 200px;
  display: grid;
}
.child {
  width: 100px;
  height: 100px;
  background: blue;
}

@container child-style (max-width: 400px) {
  .child {
    background: red;
  }
}
    </style>
<h2>container-type: inline-size</h2>
- width 크기변화:
<input type="range" value="200" id="width" name="width" min="200" max="500" onInput="onInput(event)"> <br />

<hr />

<div class="parent">
  <div class="child"></div>
</div>
<script>
const parent = document.querySelector(".parent");
function onInput(e) {
  parent.style.width = `${e.target.value}px`;
}
</script>
```
출처 : https://codepen.io/kumjungmin/pen/dymoKbX 




