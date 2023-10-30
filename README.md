##### 🍑  Front_End 과정 1단계 


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


