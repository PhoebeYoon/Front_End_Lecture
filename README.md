##### 🍑  Front_End 과정 1단계 

## What does an "&" before a pseudo element in CSS mean?

```html
 div { background-color: gold;
      &::after {  content: "\0007F7";}
      &::before { content: '\016978'}
}
<div>
  Lorem ipsum dolor sit amet consectetur adipisicing elit.
</div>
```

### & 는 sass,less 에서 사용하는 것으로 'this' 의미를 갖는다.  
이것은 순수한 css가 아니라 scss( Sass, LESS)로 css 로 변환될때 'this'의 의미로 해석된다.  

```html
 h1 { background-color: beige; }
 .ex1 { 
   & .ex2{ background-color: orange;
} 
<h1 class="ex1">heading-before
        <div class="ex2">heading-after</div>
</h1>
```



