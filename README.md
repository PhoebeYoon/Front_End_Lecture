##### 🍑  Front_End 과정 1단계 




###  writing-mode 
- horizontal-tb
- vertical-rl
- vertical-lr

### align-items vs align-content 차이   
align-items은 한 줄을 기준으로 하고
align-content는 두 줄부터 사용해야 하며 flex-wrap: wrap으로 되어 있어야 한다.  
```html
<style>
    .flex { 
    display: flex; 
    /* gap:2rem; */
    width: 600px;
    height: 800px;
    border:2px solid;
    flex-wrap: wrap;
    /* align-items:center; */
    justify-content: space-between;
    align-content:center;
    }
    .box { height: 200px; 
      width: 150px;
      font-size: 5rem;
       background-color: hsl(200,100%, 80%);
      border:3px solid hsl(200,100%, 50%);
      display: flex;
      flex-grow: 1;
  }
  </style>
</head>
<body>
  <div class="flex">
    <div class="box">1</div>
    <div class="box">2</div>
    <div class="box">3</div>
    <div class="box">4</div>
    <div class="box">5</div>
    <div class="box">6</div>
    <div class="box">7</div>
  </div>

```




