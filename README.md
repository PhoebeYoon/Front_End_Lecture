##### 🍑  Front_End 과정 1단계 


#### :peach: 데이터 속성 지정하기 
data-속성명 으로 html 태그안에 아래와 같이 넣어준다.
이때 중요한것은 속성명은 절대 camelCase  가 아닌 kebab-case 로 작성되어야한다.

속성명이 길다면 - 를 사이에 껴넣어서 표현해야한다.
이렇게 속성을 저장하였다면, 반대로 event listener 로 가져오는 방법도 알아야한다
const data = e.target.dataset

#### :peach: 데이터 속성에 접근하기

데이터 속성은 순 HTML속성이기 때문에 앞서 말했듯 CSS에서도 접근이 가능하다.
```html
<style>
article::before {
  content: attr(data-parent);
}
article[data-columns='3'] {
  width: 400px;
}
article[data-columns='4'] {
  width: 600px;
}
</style>

<section>
  id="electriccars"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars">
...
</section>

```
#### :peach: 대소문자 구분하지 않기 (i 옵션 사용하기)
```
<style>
 .message { width: 200px; background-color: lightblue;
    color:darkblue; padding:10px;
    margin-bottom: 10px;
    border-radius: 5px;
    margin-left: auto;
    margin-right: auto;  
    position: relative;
  }
.message::after{
  content: "";
  display: block;
  position: absolute;
  left:-18px; bottom: 1px;
  width: 0;height: 0;
  border-style: solid;
  border-width: 10px 20px 10px 0;
  border-color: transparent lightblue transparent transparent;
}
.message.person-2 {
  background-color: lightpink;
  color:darkred
}
.message.person-2::after {
  border-width: 10px 0 10px 20px;
  border-color: transparent  transparent transparent lightpink;
  left:auto; right:-18px;
}

.message[data-text*="hello" i]::before{
  content: "👋";
  display: inline-block;
  margin-right: 5px;
}
/*  */
</style>

 <div class="message person-1" data-text="Hello, how's it going?">Hello, how's it going?</div>
  <div class="message person-1" data-text="Are you there?">Are you there?</div>
  <div class="message person-2" data-text="Oh, HELLO there!">Oh, HELLO there!</div>
  <div class="message person-1" data-text="Welp, bye.">Welp, bye.</div>

```


#### :peach: Java Script에서 커스텀 데이터 속성에 접근하기

값을 읽기 위해서는 getAttribute()를 사용하면 된다.
```js
 var section = document.getElementById('electriccars'); 
 section.dataset.columns // "3" 
 section.dataset.indexNumber // "12314" 
 section.dataset.parent // "cars"

```



