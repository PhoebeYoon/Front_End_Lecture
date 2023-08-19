##### 🍑  Front_End 과정 1단계 




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


```



참조 : https://www.youtube.com/watch?v=ytl6TrroGis&t=143s
