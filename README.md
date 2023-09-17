##### 🍑  Front_End 과정 1단계 


### inline-size
writing-mode에 띠라 안쪽 엘리먼트의 가로/세로의 크기를 정의한다.
writing-mode가 세로이면 안쪽 엘리먼트의 너비가 width이고,   
가로이면 안쪽 엘리먼트의 너비가 height 된다,   
```html
  <style>
    /* p { writing-mode: vertical-lr;
    background-color: gold; 
    inline-size: 300px;} */
    p { writing-mode: horizontal-tb;
    background-color:pink; 
    inline-size: 500px;
    /* 사이즈를 지정하기 않으면 p가 블록속성이므로 원래 d의 속성대로 작동한다 */
  }
  </style>
  <p>Start- Lorem ipsum dolor sit amet consectetur adipisicing elit.
Accusamus quis expedita praesentium similique quia nam repellat
quas id facilis obcaecati quisquam ea sed, quaerat voluptatum
doloremque suscipit mollitia minus exercitationem! -- End</p>
```
