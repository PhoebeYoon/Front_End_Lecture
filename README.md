##### 🍑  Front_End 과정 1단계 


## :nth-child( 2 of something) 
그전에 사용하던 ``` article > .clr-accent:nth-of-type(2) ``` 이 작동되지 않는다. 대신 아래와 같이 사용해야한다.   

```html
    <style>
    .clr-accent { color:dodgerblue}
      article > :nth-child(1 of .clr-accent) { text-decoration: underline;
        color:red; font-size: 1.5rem;}
    </style>
    <article>
        <h1 class="article-title">  <code>:nth-child getting better</code></h1>
        <p class="clr-accent">Lorem ipsum dolor sit amet consectetur</p>
        <p>Lorem ipsum dolor sit amet consectetur</p>
        <p class="clr-accent">Lorem ipsum dolor sit amet consectetur</p>
        <p class="clr-accent">Lorem ipsum dolor sit amet consectetur</p>
        <p>Lorem ipsum dolor sit amet consectetur</p>
        <p class="clr-accent">Lorem ipsum dolor sit amet consectetur</p>
        <p>Lorem ipsum dolor sit amet consectetur</p>
        <p class="clr-accent">Lorem ipsum dolor sit amet consectetur</p>
    </article>
```


