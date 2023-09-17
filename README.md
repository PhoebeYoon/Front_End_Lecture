##### 🍑  Front_End 과정 1단계 


### margin-inline   
write-mode 에 따라 margin의 값이 달라진다.   

margin-inline: 10px; 좌우모두 같은 값을 적용하고   
margin-inline: 10px 50px 는 좌우를 다르게 지정한다  
위의 내용을 shortcut버전이고 아래의 내용과 동일하다 
margin at start is 10px   
margin at end is 50px    


```html
<style>
#parentDIV {
  width: 60%;
}

#parentDIV > div {
  writing-mode: vertical-rl;
  block-size: 100%;
  box-sizing: border-box;
}

.redDiv {
  background-color: rgb(239, 135, 88);
  inline-size: 10%;
}

#myDIV {
  background-color: lightblue;
  inline-size: 30%;
  border: solid black 1px;
  margin-inline: 10px 50px;
}
</style>
</head>
<body>

<h1>The margin-inline Property</h1>
<p>Here, the margin-inline property is affected by the CSS writing-mode property.</p>

<div id="parentDIV">
  <div class="redDiv">div</div>
  <div id="myDIV">
    <p>This DIV element has a margin of 10 pixels from start of DIV element
in the inline direction, and 50 pixels margin from the end.</p>
  </div>
  <div class="redDiv">div</div>
</div>
```

```html

<style>
div {
  background-color: rgb(239, 135, 88);
  width: 25%;
  height: 250px;
  float: left;
}

#ex1 {
  background-color: lightblue;
  border: solid black 1px;
  margin-inline: 10px 50px;
 /*  direction: rtl; */
}
</style>
</head>
<body>

<h1>The margin-inline Property</h1>
<p>Here, the margin-inline property is affected by the CSS direction property.</p>

<div>A div element with no specified margins.</div>

<div id="ex1">This DIV element has a margin of 10 pixels from start
of DIV element in the inline direction, and 50 pixels margin from the end.</div>

<div>A div element with no specified margins.</div

```







