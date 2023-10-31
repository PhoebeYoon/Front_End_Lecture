##### 🍑  Front_End 과정 1단계 

```
/* Block component */
.btn {}

/* Element that depends upon the block */ 
.btn__price {}  // 하위 항목 또는 요소는 내부에 배치될 수 있으며
                // .btn__price { }와 같이 블록 이름 뒤에 두 개의 밑줄로 표시됩니다

/* Modifier that changes the style of the block */ 
.btn--orange {}  
.btn--big {} 
// 변경을 가하지 않고 해당 특정 구성 요소를 테마화하거나 스타일화할 수 있습니다.
// 이는 btn-orange와 마찬가지로 블록 이름에 두 개의 하이픈을 추가함으로써 수행됩니다.
```

[예제]

```html
   <style>
        /* Block */
.btn {
  text-decoration: none;
  background-color: white;
  color: #888;
  border-radius: 5px;
  display: inline-block;
  margin: 10px;
  font-size: 18px;
  text-transform: uppercase;
  font-weight: 600;
  padding: 10px 5px;
}

/* Element */
.btn__price {
  background-color: white;
  color: #fff;
  padding-right: 12px;
  padding-left: 12px;
  margin-right: -10px; /* realign button text padding */
  font-weight: 600;
  background-color: #333;
  opacity: .4;
  border-radius: 5px 0 0 5px;
}
/* Element */
.btn__text {
  padding: 0 10px;
  border-radius: 0 5px 5px 0;
}
/* Modifier */
.btn--big {
  font-size: 28px;
  padding: 10px;
  font-weight: 400;
}

/* Modifier */
.btn--blue {
  border-color: #0074D9;
  color: white;
  background-color: #0074D9;
}

/* Modifier */
.btn--orange {
  border-color: #FF4136;
  color: white;
  background-color: #FF4136;
}

/* Modifier */
.btn--green {
  border-color: #3D9970;
  color: white;
  background-color: #3D9970;
}
body {
  font-family: "fira-sans-2", sans-serif;
  background-color: #ccc;
}
    </style>

<a href="https://css-tricks.com" class="btn">
        <span class="btn__text">Standard button</span>
      </a>
      
      <a href="https://css-tricks.com" class="btn btn--orange btn--big">
        <span class="btn__price">$3</span>
        <span class="btn__text">Big button</span>
      </a>
      
      <a href="https://css-tricks.com" class="btn btn--blue btn--big">
        <span class="btn__price">$4</span>
        <span class="btn__text">Big button</span>
      </a>
      
      <a href="https://css-tricks.com" class="btn btn--green btn--big">
        <span class="btn__price">$9</span>
        <span class="btn__text">Big button</span>
      </a>

```


