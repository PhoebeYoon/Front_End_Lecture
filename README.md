##### 🍑  Front_End 과정 1단계 


#### 1.  데이터 속성 지정하기 
data-속성명 으로 html 태그안에 아래와 같이 넣어준다.
이때 중요한것은 속성명은 절대 camelCase  가 아닌 kebab-case 로 작성되어야한다.

속성명이 길다면 - 를 사이에 껴넣어서 표현해야한다.
이렇게 속성을 저장하였다면, 반대로 event listener 로 가져오는 방법도 알아야한다
const data = e.target.dataset

#### 2. 데이터 속성에 접근하기

데이터 속성은 순 HTML속성이기 때문에 앞서 말했듯 CSS에서도 접근이 가능하다.
```html
<style>
article::before {
  content: attr(data-parent);
}
article[data-columns='3'] {
  width: 400px; background-color: #ff0 
}
article[data-columns='4'] {
  width: 600px; background-color: #f00 
}
</style>

<section>
   <article id="electriccars"
  data-columns="3" 
  data-index-number="12314"  
  data-parent="cars">
...
</section>

```
이렇게하고  article 태그안의 data-columns의 값에 따라 css가 바뀐다.  
**😠**  주의: data-index-number를 가져올때는 dataset.index-number (X) 아니고 dataset.indexNumber(O) 로 적어야 한다.


##### 위의 내용을  JavaScript에서 커스텀 데이터 속성에 접근하면 아래와 같다 (값을 읽기 위해서는 getAttribute()를 사용)
article.dataset에는 columns, indexNumber, parent 의 값이 모두 들어있다.   

```js
 var section = document.getElementById('electriccars'); 
 console.log(section.dataset.columns)// "3" 
 console.log(section.dataset.indexNumber)// "12314" 
 console.log(section.dataset.parent) // "cars"
```

[참조](https://css-tricks.com/a-complete-guide-to-data-attributes/ )



좀더 많은 내용으로 해보자면,  



```html
<style>
[data-columns] {
  display: grid;  grid-gap: 1rem;  padding: 1rem;
  margin: 0 0 1rem 0;}

[data-columns] > div {
  height: 100px;  background: white; }

[data-columns="2"] {
  background: #64B5F6;  grid-template-columns: repeat(2, 1fr);}

[data-columns="3"] {
  background: #9CCC65;  grid-template-columns: repeat(3, 1fr);}

[data-columns="4"] {
  background: #FFB74D;  grid-template-columns: repeat(4, 1fr);}
body {  margin: 1rem;}
</style>
<div data-columns="2">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>

<div data-columns="3">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>

<div data-columns="4">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

#### 3. 대소문자 구분하지 않기 (i 옵션 사용하기)
아래의 예는 hello가 들어간 문장에 손흔드는 이모지 삽입해주는 것이다. 
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

```
<style>
[data-emoji]::before {
  content:attr(data-emoji);
  margin-right:5px;
}
/* ✅가 리턴된다 */
</style>
<div data-emoji="✅"></div>
```





