##### 🍑  Front_End 과정 1단계 
### :peach: padding-block, padding-inline
padding-block은 기존의 padding-top, padding-bottom, padding-left, padding-right와 매우 비슷하지만   
해당 요소가 block 또는 inline 인지에 따라 달라집니다.   
그래서 __block은 downward 방향이고 inline은 왼쪽에서 오른쪽방향이라고 생각하시면 됩니다.__ 

padding-block: 10px 50px은   
padding at start is 10px   
padding at end is 50px 의미입니다  

padding-inline : 10px 이라고 하면 좌우의 여백 10px 적용됩니다   

```html
<html>
<head>
<style>
div {
  border: 1px solid red;
  box-sizing: border-box;
  width: 300px;
}

div.ex1 {
  margin-bottom: 20px;
  padding-inline: 50px;
  padding-block: 20px;
}
</style>
</head>
<body>

<h1>The padding-inline Property</h1>

<div class="ex1">This div element has a padding of 50 pixels at the start and end in the inline direction.</div>

<div>This div element has no specified padding.</div>
</body>
```

inline 방향에서  padding 끝에 적용되는 값을 지정한다  
```html
<style>
div { border: 1px solid red;
  box-sizing: border-box; width: 300px; }
div.ex1 { margin-bottom: 20px;
  padding-inline-end: 50px; 
/*  padding-inline-start: 50px; */
  }
</style>
</head>
<body>

<h1>The padding-inline-end Property</h1>
<div class="ex1">This div element has a padding of 50 pixels at the end in the inline direction.</div>
<div>This div element has no specified padding.</div>

```
