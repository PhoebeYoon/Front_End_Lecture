##### 🍑  Front_End 과정 1단계 

## Window.getComputedStyle()
Window.getComputedStyle() 메소드는 인자로 전달받은 요소의 모든 CSS 속성값을 담은 객체를 회신합니다.   
이 속성값들은, 해당 요소에 대하여 활성 스타일시트와 속성값에 대한 기본 연산이 모두 반영된 결과값입니다.   
[작성법]    
```
var style = window.getComputedStyle(속성값을 얻으려는 element [, pseudoElt]);
 - pseudoElt : 일치시킬 의사요소(pseudo element)를 지정하는 문자열. 보통의 요소들에 대해서는 생략되거나 null이어야 함.
```
반환되는 스타일은 요소의 스타일이 변경 될때 자동으로 업데이트 되는 실시간 css style 객체이다.  

```js
    <style>
p { width: 400px;  margin: 0 auto;
  padding: 20px; line-height: 2;
  font-size: 2rem; font-family: sans-serif;
  background: purple; color: white;
  text-align: center;
}
    </style>
    <p>Hello</p>
<script>
    let para = document.querySelector('p');
    let compStyles = window.getComputedStyle(para);

    para.textContent = "My computed font-size is " +
  compStyles.getPropertyValue("font-size") +
  ",\nand my computed line-height is " +
  compStyles.getPropertyValue("line-height") +
  ".";
</script>

```
다른 예,

```js
<style>
  h3::after {
    content: " rocks!";
  }
</style>

<h3>generated content</h3>

<script>
  var h3 = document.querySelector("h3");
  var result = getComputedStyle(h3, ":after").content;

  console.log("the generated content is: ", result); // returns ' rocks!'
</script>

```



