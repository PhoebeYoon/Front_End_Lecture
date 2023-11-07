##### 🍑  Front_End 과정 1단계 

display:-webkit-box    
-webkit-line-clamp   
-webkit-box-orient : vertical    
overflow: hidden   


```html
<body>
  <section class="card-group">
    <article class="card " >
      <h2>Article 1</h2>
      <p class="cutoff-text">Lorem ipsum dolor sit amet conses?</p>
      <input class="expand-btn" type="checkbox">
    </article>
    <article class="card" >
      <h2>Article 2</h2>
      <p class="cutoff-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem sequi soluta beatae magni culpa ab accusantium vero nihil quia ducimus ratione aut, error pariatur, reprehenderit placeat, ipsa corruhil quia ducimus ratione aut, error pariatur, reprehenderit placeat, ?</p>
     
      <input class="expand-btn" type="checkbox">
    </article>
    <article class="card" >
      <h2>Article 3</h2>
      <p class="cutoff-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem sequi soluta beatae magni culpa ab accusantium vero nihil quia ducimus ratione aut, error pariatur, reprehenderit placeat, ipsa corruhil quia ducimus ratione aut, error pariatur, reprehenderit placeat, ipsa cor</p>
     
      <input class="expand-btn" type="checkbox">
    </article>
  </section>
</body>

```   
cutoff-text라는 클래스안에 모든 내용이 들어가 있어야 한다   

```css
   *, *::after, *::before { box-sizing: border-box;}
    body { background: #f3f3f3; overflow: hidden;}
    .card-group { display: grid; 
    grid-template-columns: repeat(3, 1fr);
      gap : .5rem;
      align-items: flex-start;
  }
  .card { background: white; padding: 1rem;
    border:1px solid black; border-radius: .25em;}
    h2,p { margin: 0;}
    h2 { margin-bottom: 1rem;}

.cutoff-text { 
  --max-lines:5;
  --line-height : 1.4;

  /* display: -webkit-box; */
  overflow: hidden;
  height: calc( var( --max-lines) * 1em * var(--line-height));
 
  line-height: var(--line-height);

  /* -webkit-line-clamp: var(--max-lines);
  -webkit-box-orient: vertical; */
  position: relative;
}
.cutoff-text:has(+ .expand-btn:not(:checked))::before {
/* .cutoff-text:has(+ .expand-btn:not(:checked))::before {  */
 content: "";
 position: absolute; 
 height: calc(2em * var(--line-height)); 
 width: 100%; bottom: 0; 
 pointer-events: none;
 background: linear-gradient(to bottom, transparent, white);
}

.expand-btn { appearance: none; 
  border:1px solid black; padding:  .5em;
  border-radius: .25em; cursor: pointer; margin-top: 1rem;;
}
.expand-btn:hover { background-color: #ccc;}
.expand-btn::before { content:"Expand"}
.expand-btn:checked::before { content:"Collapse"}

.cutoff-text:has(+ .expand-btn:checked) {
  height:auto;
}

```

### appearance에 대해

외관 CSS 속성은 운영체제의 테마에 따라 플랫폼별 스타일링으로 UI 요소를 표시하는 데 사용됩니다.
표준화 전에는 이 속성을 통해 button 또는 checkbox과 같은 요소를 위젯으로 표시할 수 있었습니다.   

<img width="600" alt="스크린샷 2023-06-08 오후 10 49 24" src="https://github.com/PhoebeYoon/HTML/assets/48478079/933a0912-f560-4ba9-a47f-e91e2a17c721">

