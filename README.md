##### 🍑  Front_End 과정 1단계 

## The difference between attributes and properties in vanilla JS


브라우저가 페이지를 로드할 때 HTML을 "읽고"(parse) DOM 오브젝트들을 생성합니다.   
엘리먼트 노드의 경우,  대부분의 표준 HTML 속성이 자동으로 DOM 객체의 속성이 됩니다.   
그러나 attribute-property 가 1:1로 매칭되는 것은 아닙니다.  

아래는 기본내용을 다룹니다. 
```html
<p>Hello</p>

    <label for="greeting">Greeting</label>
    <!-- 1.  -->
    <input type="checkbox" id="greeting2">
    <!-- 2. -->
    <input type="text" id="greeting">

    <script>
        let p = document.querySelector('p');
        // Update the ID
        p.setAttribute('id', 'first-paragraph');

        // These both return "first-paragraph"
        let id1 = p.getAttribute('id');
        let id2 = p.id;
        console.log( id1, id2)


        // 1. However, user-changeable form properties—noteably, 
        // value, checked, and selected—are not automatically synced.
        let greeting2 = document.querySelector('#greeting2');
         greeting2.setAttribute('checked' ,'yes')

       
         // 2. type=text는 user-changeable 이므로 아래의 내용이 되질 않는다
         let greeting= document.querySelector('#greeting');
         greeting2.setAttribute('checked' ,'yes')

         // Update the value
          greeting.setAttribute('value', 'Hello there!');
          let val1 = greeting.value;
          let val2 = greeting.getAttribute('value');
          console.log( 'val1 : ' , val1 , ', val2 :',val2)

          greeting.value = 'Bye~~!';

    </script>

```
## DOM properties ,HTML attributes 로 일단 이해하자
### DOM properties를 이용하여 아래의 내용을 시도해보자
따라서 DOM 속성과 메서드는 일반 자바스크립트 객체와 동일하게 동작하며, 어떤 value도 가질 수 있습니다. 이것들은 대소문자를 구분하니 주의합니다.
```js
<script>
document.body.myData = {
  name: 'Caesar',
  title: 'Imperator'
};
alert(document.body.myData.title)

// 메소드를 추가할 수도 있다
document.body.sayTagName = function(){
    alert(this.tagName)
}
document.body.sayTagName();


// 위의 추가한 메소드를 built-in 처럼 사용하고자 한다면
Element.prototype.sayHi = function(){
    alert(` Hello, I'm ${this.tagName}`)

}
document.documentElement.sayHi();
document.body.sayHi();
    </script>

```

### html attributes   

태그는 속송들을 가질 수 있다. 브라우저가 html를 파싱하여 태그를 위해 DOM 오브젝트를 생성할때, 이것들은 표준 DOM properties와 attributes를 인지한다.   
그러므로 엘리먼트는 id 또는 다른 표준 attribute, 만들어진 the corresponding property를 가질 수 있지만 속성이 비표준인 경우에는 해당 속성이 생성되지 않는다.  













