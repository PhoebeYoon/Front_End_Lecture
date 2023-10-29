##### 🍑  Front_End 과정 1단계 

## style.setProperty(속성이름, value, priority)   

priority에는 ```  important / undefined, String empty value ""  이 들어갈 수 있다  ```    

```html
<style>
    html {
  background: orange;
  font-family: sans-serif;
  height: 100%;
}

body {
  height: inherit;
  width: 80%;
  min-width: 500px;
  max-width: 1000px;
  margin: 0 auto;
}

.controls {
  display: flex;
  justify-content: space-around;
  align-items: center;
}
  </style>
<div class="controls">
    <button class="border">Border</button>
    <button class="bgcolor">Background</button>
    <button class="color">Text</button>
</div>
<div class="box">
    <p>Box</p>
</div>

  <script>
const borderBtn = document.querySelector(".border");
const box = document.querySelector(".box")
borderBtn.addEventListener('click', ()=>{
  box.style.setProperty("border", "5px dashed green");
})
  </script>

```

위의 내용에서 추가한다.  
```
<style>
html {
  background: orange;font-family: sans-serif;
  height: 100%;
}
body { height: inherit;
  width: 80%; min-width: 500px;
  max-width: 1000px; margin: 0 auto;
}
.controls { display: flex;
  justify-content: space-around;
  align-items: center; }

div button { flex: 1;
  margin: 20px; height: 30px;
  line-height: 30px; }
.box { display: flex;
  justify-content: center;
  align-items: center; height: calc(100% - 70px); }
.box p { width: 50%; text-align: center;
  font-weight: bold; font-size: 40px;
  height: 150px; line-height: 150px;
  background: red; border: 5px solid purple;
  color: white; transition: all 1s;
}
</style>
<script>
const borderBtn = document.querySelector(".border");
const bgColorBtn = document.querySelector(".bgcolor");
const colorBtn = document.querySelector(".color");
const box = document.querySelector(".box");

function random(min, max) {
  const num = Math.floor(Math.random() * (max - min)) + min;
  return num;
}
function randomColor() {
  return `rgb(${random(0, 255)}, ${random(0, 255)}, ${random(0, 255)})`;
}

console.log(randomColor())
// rgb(숫자)로 색상이 지정된다.


const stylesheet = document.styleSheets[0]
const boxParaRule = [...stylesheet.cssRules]  // 1번
// 이렇게 해서 스타일의 내용을 배열형태로 저장한다
// 0 :  CSSStyleRule {selectorText: 'html', style: CSSStyleDeclaration, ~
// 1 : CSSStyleRule {selectorText: 'body', style: CSSStyleDeclaration, ~
// 2 : CSSStyleRule {selectorText: '.controls', style: CSSStyleDeclaration,~ 
// 3 : CSSStyleRule {selectorText: 'div button', style: CSSStyleDeclaration,~ 
// 4 : CSSStyleRule {selectorText: '.box', style: CSSStyleDeclaration,~
// 5 : CSSStyleRule {selectorText: '.box p', style: CSSStyleDeclaration,~ 

// 1번을 주석처리하고 아래와 같이 바꾼다.
const boxParaRule = [...stylesheet.cssRules].find( (r)=> 
 // console.log(r.selectorText)
 // 결과는 클래스명과 태그명이 출력된다 
  r.selectorText ===".box p"
)
// .box p 있다면 이것을 boxParaRule에 저장한다.
console.log( boxParaRule )


// 이제 "Border"버튼를 클릭하면 border가 설정되고 , Background 버튼을 클릭하면 배경 ,
// Text 버턴을 클릭하면 글자가 설정되도록 한다

function setRandomBorder(){
 const newBorder = `${random(1, 50)}px solid ${randomColor()}`;
  boxParaRule.style.setProperty('border', newBorder)
}

function serRandomBgColor(){
  const newBgColor = randomColor(); 
  boxParaRule.style.setProperty('background-color', newBgColor)
}

function setRandomColor(){
  const newColor = randomColor();
  boxParaRule.style.setProperty("color", newColor)
}

borderBtn.addEventListener('click', setRandomBorder)
bgColorBtn.addEventListener('click', serRandomBgColor)
colorBtn.addEventListener('click', setRandomColor)

</script>
```



