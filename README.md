##### 🍑  Front_End 과정 1단계 

- scroll-snap-align : none, start, end, block inline, initial, inherit
- scroll-snap-stop : normal, always, initial, inherit
- scroll-snap-type : 아래에  


### 1. scroll-snap-type   
기본 values :   
scroll-snap-type: none;   
scroll-snap-type: x;  
scroll-snap-type: y;   
scroll-snap-type: block;   
scroll-snap-type: inline;   
scroll-snap-type: both;   

/* Optional mandatory (형용사, 법에 정해진, 의무적인) | proximity (명사, 거리,시간상으로 가까움) */
> 그러니까 proximity는 거리상으로 50%가 넘어야 다음 페이지로 스냅되어서 넘어가고   
> mandatory는 조금만 당겨도 다음 페이지로 넘어간다로 생각하자

scroll-snap-type: x mandatory;   
scroll-snap-type: y proximity;   
scroll-snap-type: both mandatory;   

/* Global values */   
scroll-snap-type: inherit;   
scroll-snap-type: initial;  
scroll-snap-type: revert;   
scroll-snap-type: revert-layer;  
scroll-snap-type: unset;   
 



```html
  <style>
* {margin: 0;padding: 0;}
div { display: flex; 
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;} 
html { scroll-snap-type: y mandatory;} 
nav { line-height: 30px; 
    width: 100%; 
    background:gray;
    text-align: center;
    position: sticky;
    top:0; z-index: 99;
    color:beige; }
section{ height: 100vh; 
  scroll-snap-align:start ;
  scroll-snap-stop: normal;
  scroll-margin-top: 30px; }
  </style>

<nav>Heading</nav>
  <div>
    <section style="background-color: red;">
      <h2>Page1</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis aperiam adipisci amet nihil cumque a voluptates veritatis sit quod ullam, architecto enim recusandae quisquam! Quaerat illo corporis vero distinctio ipsam?</p>
    </section>
    <section style="background-color: orange;"> 
      <h2>Page2</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis aperiam adipisci amet nihil cumque a voluptates veritatis sit quod ullam, architecto enim recusandae quisquam! Quaerat illo corporis vero distinctio ipsam?</p>
    </section>
    <section style="background-color: green;">
      <h2>Page3</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis aperiam adipisci amet nihil cumque a voluptates veritatis sit quod ullam, architecto enim recusandae quisquam! Quaerat illo corporis vero distinctio ipsam?</p>
    </section>


    <section style="background-color: gold;">
      <h2>Page4</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis aperiam adipisci amet nihil cumque a voluptates veritatis sit quod ullam, architecto enim recusandae quisquam! Quaerat illo corporis vero distinctio ipsam?</p>
    </section>


    <section style="background-color: pink">
      <h2>Page5</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis aperiam adipisci amet nihil cumque a voluptates veritatis sit quod ullam, architecto enim recusandae quisquam! Quaerat illo corporis vero distinctio ipsam?</p>
    </section>
  </div>

<!-- 위의 예제에서 다음 페이지로 넘어갈때 중간이후에 페이지가 서서히 멈추면서 어떻게 스냅이 되는지 확인해 보자 -->
```



참조 :  https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type   
https://www.youtube.com/watch?v=ytl6TrroGis&t=143s
