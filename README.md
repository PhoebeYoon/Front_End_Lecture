##### 🍑  Front_End 과정 1단계 

## 특정클래스의 순서를 선택할때 

```html
 <style>
 * {font-size: 20px;}
.red { color:red}
/* .list li:nth-child(5) { text-decoration: underline; color:green} */
.list :nth-child(5) { color:green}
.list :nth-child(5)  { text-decoration: underline;}

/* .list .red:nth-child(2 ) { text-decoration: line-through;} 적용되지 않는다  아래설명참조*/
.list :nth-child(2 of .red){ text-decoration: line-through;}
.list :nth-child(2n+1 of .red){ font-weight: 900;}
    </style>
<body>
    <ul class="list">
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
    </ul>
</body>
```
위의 내용에서  "언급된 설명"처럼 ``` .list .red:nth-child(2 ) { text-decoration: line-through; ```은 적용되지 않는다
list클래스 아래에 있는 red클래스에서 2번째것만 바꾸고 싶다면
```  .list :nth-child(2 of .red){ text-decoration: line-through;}  ``` 와 같이 언급해주어야 한다. 또한  
``` .list :nth-child(2n+1 of .red){ font-weight: 900;}  ``` 와 같이 짝수, 홀수와 같은 표현을 사용할 수도 있다.
