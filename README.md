##### 🍑  Front_End 과정 1단계 

## ::marker

```html
  <style>
        /* ::marker { color:teal} */
        
        /* ::marker{
            content:'[' counter(list-item) ']'; 
            color:crimson;
            font-weight:bold;
        } */
        /* list-item는 따로 설정할 필요없이 list-style-type에서 주어진다 */

        /* li { list-style-type: '😀';
        padding-left: 1ch; } */

      li { list-style-type: '★'; }
      ::marker { color:crimson}

    </style>
    <ol>
        <li>I am an an ordered list</li>
        <li>My markers are styled via ::marker</li>
        <li>The gap size is 1ch</li>
      </ol>
</body>
```
li에 있는 별표는 한글 'ㅁ' + 한자키를 조합해서 만듦. 
