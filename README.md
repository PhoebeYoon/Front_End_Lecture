##### 🍑  Front_End 과정 1단계 


## place-content속성은 flexbox와 grid layout에서 사용되며, align-content, justify-content의 단축입니다 

```html
<!DOCTYPE html>
<html>
<head>
<style>
#container { height: 350px; width: 60%;
  border: solid black 1px;
  display: flex; flex-wrap: wrap;
  /* justify-content: space-between;
  align-items:flex-end; */
  place-content: end space-between;
}
#container > div { flex-basis: 40px;
  height: 40px; margin: 2px;
  background-color: coral; }
</style>
</head>
<body>
<div id="container">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>

</div>
</body>
</html>
```     
<img width="300" alt="스크린샷 2023-06-10 오후 10 54 51" src="https://github.com/PhoebeYoon/HTML/assets/48478079/b8ad276a-e5eb-4a18-b2cc-262591df6f0f">
<img width="300" alt="스크린샷 2023-06-10 오후 10 55 32" src="https://github.com/PhoebeYoon/HTML/assets/48478079/8cca8507-eec7-4686-8b4c-36fa55f37377">

## place-items는 align-items (flex) 와 justify-items (grid) 의 축약이라고 할 수 있다   
그러니까 place-items를 사용하면 flex와 grid를 하나의 명령어로 컨트롤할 수 있게 되는 것이다.   
만약 place-items: start center; 라고 할때 align-items 속성은 'start'이고 'justify-items'는 'center'가 되는 것이다. 









