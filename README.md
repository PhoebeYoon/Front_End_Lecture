##### 🍑  Front_End 과정 1단계 

#### writing-mode Property     
살짝 헷갈릴 수 있는 내용입니다. horizontal이라면 일반적인 경우로 해석됩니다.    
왼쪽 --> 오른쪽,   
위--> 아래   
vertical로 적혀있다면 vertical 뒤에 있는 rl 또는 lr 가 방향을 결정한다고 생각하면 됩니다.    

writing-mode의 속성은  

| value | 설명 |
|---|---|
| horizontal-tb | 수평방향에서는 왼쪽에서 오른쪽 , 수직방향에서는 위에서 아래 |
| vertical-rl |	수평적으로 오른쪽--> 왼쪽,  수직적으로  위--> 아래 |
| vertical-lr	|  수평적으로 왼쪽--> 오른쪽, 수직적으로  위--> 아래 |

```
  <style> 
  /* p { writing-mode: horizontal-tb;} */
  p { writing-mode: vertical-lr}
  </style>
 <body>
   <p> 글자의 방향을 확인해보세요 한글과 alphabet</p>
</body>
```
```
<style>
    p { writing-mode: horizontal-tb;}
    span.test1 { writing-mode: vertical-rl;}
</style>
<p>Some text with a span element with a <span class="test1"> alphabet</span> writing-mode.</p>
```

 ```
<style>
    body {
      background-color:#E7E9EB;
    }
    #myDIV {
      height:300px;
      background-color:#FFFFFF;
      writing-mode: vertical-lr;
    }
    </style>
<body>
  <div id="myDIV">
    Check what you can do with the writing-mode property!
    </div>
    <!-- 글자가 시작되는 방향을 확인하세요 -->
</body>
```
