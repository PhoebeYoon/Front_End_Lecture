##### 🍑  Front_End 과정 1단계   
1. place-content   
2. place-items   
3. place-self   
위의 내용은 flexbox와 grid layout에서 사용됩니다.   


## place-content속성은 align-content, justify-content의 단축입니다 


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
<img width="300" alt="스크린샷 2023-06-10 오후 11 24 45" src="https://github.com/PhoebeYoon/HTML/assets/48478079/6f87dfbf-4a92-467b-a38c-f63aac8f1392">

<img width="200" alt="스크린샷 2023-06-10 오후 10 55 32" src="https://github.com/PhoebeYoon/HTML/assets/48478079/8cca8507-eec7-4686-8b4c-36fa55f37377">

## place-items는 align-items (flex) 와 justify-items (grid) 의 축약이라고 할 수 있다   
그러니까 place-items를 사용하면 flex와 grid를 하나의 명령어로 컨트롤할 수 있게 되는 것이다.   
만약 place-items: start center; 라고 할때 align-items 속성은 'start'이고 'justify-items'는 'center'가 되는 것이다.    

☑️ place-items: stretch end 가 flexbox 에 사용된다면 justify-items는 flexbox와 관계없는 속성이기 때문에 2번째 속성은 무시된다.

## place-self는 align-self, justify-self 의 축약입니다.  

```html
<!DOCTYPE html>
<html>
<head>
<style>
#container { width: 60%;
  aspect-ratio: 1/2; border: solid black 1px;
  display: flex;
  flex-wrap: wrap;
  place-items: start; 
}
#container > div { padding: 40px; margin: 2px; }
.normalDiv { background-color: coral; }
#myDiv {
  border: solid black 3px;
  background-color: lightgreen;
  place-self: end stretch; }
</style>
</head>
<body>
<div id="container">
  <div class="normalDiv"></div>
  <div class="normalDiv"></div>
  <div id="myDiv"></div>
  <div class="normalDiv"></div>
  <div class="normalDiv"></div>
  <div class="normalDiv"></div>
  <div class="normalDiv"></div>
</div>
</body>
</html>
```     
<img width="300" alt="스크린샷 2023-06-10 오후 11 37 27" src="https://github.com/PhoebeYoon/HTML/assets/48478079/ad4c5397-c36a-4985-9361-c2a38ca23adb">

☑️ place-self속성은 flexbox items을 위한 것이지만 두번째 값인 justify-self는 flexbox와 관련된 항목이 아니므로 무시된다






