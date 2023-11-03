##### 🍑  Front_End 과정 1단계 


## @container  
viewport가 아닌 특정 요소의 크기에 따라 스타일링을 할 수 있는 container 쿼리이다.
컨테이너 컨텍스트에 스타일을 적용하는 조건부 그룹 규칙이다.  
스타일 선언은 조건에 따라 필터링되고 조건이 true이면 컨테이너에 적용된다. 조건은 컨테이너 크기가 변경될 때 평가된다.  
스타일 선언은 해당 컨테이너의 컨텍스트에서만 유효하다. 즉, 컨테이너의 하위 요소들에게만 유효하다   

형식  
```
@container [ <container-name> ]? <container-condition> { <stylesheet> }
```

[예제] 

```html
  <style>
  .parent {
  container-type: inline-size;
  container-name: child-style;
  border: 3px solid gray;
  width: 200px;
  height: 200px;
  display: grid;
}
.child {
  width: 100px;
  height: 100px;
  background: blue;
}

@container child-style (max-width: 400px) {
  .child {
    background: red;
  }
}
    </style>
<h2>container-type: inline-size</h2>
- width 크기변화:
<input type="range" value="200" id="width" name="width" min="200" max="500" onInput="onInput(event)"> <br />

<hr />

<div class="parent">
  <div class="child"></div>
</div>
<script>
const parent = document.querySelector(".parent");
function onInput(e) {
  parent.style.width = `${e.target.value}px`;
}
</script>
```
출처 : https://codepen.io/kumjungmin/pen/dymoKbX 

[예제] 
```html

    <style>
        /* 
// Container Query things are at the bottom!
// Scroll down!
*/ 

/* Not CQ Things */
:root {
  --accentColor: #7531ff;
}

body {
  font-family: 'Google Sans', system-ui, serif;
  line-height: 1.5;
  padding: 2rem 1rem;
}

.page-container {
  display: grid;
  grid-template-columns: 35% 1fr;
  gap: 1rem;
}

img {
  width: 100%;
}

.card {
  display: grid;
  grid-template-columns: 40% auto;
  gap: 2rem;
  margin: 0 auto;
  border: 1px solid var(--accentColor);
  padding: 1rem;
}

.card-container:before {
  content: attr(data-size);
  position: absolute;
  left: 0;
  right: 0;
  top: -0.6rem;
  width: 6ch;
  margin: 0 auto;
  text-align: center;
  display: inline-block;
  background: var(--accentColor);
  color: white;
}

h2 {
  font-size: 2.5rem;
  font-weight: 400;
  line-height: 1;
}

h3 {
  font-size: 1.15rem;
  font-weight: 800;
  text-transform: uppercase;
  margin: 1rem 0 0.25rem;
  line-height: 1;
}

a {
  color: var(--accentColor);
}

.time {
  font-size: 1.5rem;
  font-weight: 300;
}

button {
  border: none;
  padding: 0.5rem;
  background: var(--accentColor);
  color: white;
  font-weight: 600;
  letter-spacing: 0.1rem;
  text-transform: uppercase;
  margin-top: 1rem;
}
/* End Not CQ Things */

/* 
// Container Query things are here!
*/ 

/* First, set containment on the parent you're querying*/
.card-container {
  container-type: inline-size;
}

/* Then, you can style the parent's children based on its width */
@container (max-width: 850px) {
  .links {
    display: none;
  }
  
  .time {
    font-size: 1.25rem;
  }
  
  h2 {
    font-size: 2.2rem;
  }
}

@container (max-width: 650px) {
  .desc {display: none; }
  h2 { font-size: 2rem; }
  .card { gap: 1rem;}
}

@container (max-width: 460px) {
  .card {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 0.5rem;
  }
  
  button {
    display: block;
    margin: 1rem auto 0;
  }
}

@container (max-width: 300px) {
  h2 {font-size: 1.5rem;} 
  .time {display: none;}
}
.warning {
  max-width: 460px;
  margin: 2rem auto;
  background: #ffcebf;
  border: 1px solid tomato;
  padding: 1rem;
}

strong {font-weight: 800;}
i {font-style: italic;}

@supports (container-type: inline-size) {
  .warning {display: none;}
}
    </style>
    <div class="warning"><strong>Warning:</strong> Your browser does not support CSS container queries. Please open this demo in Chrome Canary with the experimental <i>#enable-container-queries</i> flag turned on.</div>


<div class="page-container">
  <div class="card-container card-1" data-size="0">
    <div class="card">
      <figure>
        <img src="http://static.libsyn.com/p/assets/9/8/1/c/981c2ef87dd4c9e7/TCP000_thumbnail_v3.png" />
      </figure>
      <div>
        <div class="meta">
          <h2>Preference Media Queries</h2>
          <span class="time">15:40</span>
        </div>

        <div class="notes">
          <p class="desc">In this episode we narrow our focus on user-preference-based media queries, which enable you to create personalized experiences based on your users custom settings and needs.</p>
          <div class="links">
            <h3>Links</h3>
            <ul>
              <li>Media Queries → <a href="#">http://goo.gle/2MhYfR2</a></li>
              <li>Scripting → <a href="#">http://goo.gle/2Mdan5E</a></li>
              <li>The 'display-mode' media feature → <a href="#">http://goo.gle/2NoFr3c</a></li>
              <li>Prefers-* Security and Privacy → <a href="#">http://goo.gle/3kfwUM0</a></li>
              <li>CSS Color Adjustment → <a href="#">http://goo.gle/3qLkduJ</a></li>
            </ul>
          </div>
        </div>

        <button>Download Episode</button>
      </div>
    </div>
  </div>
  <div class="card-container card-2" data-size="0">
    <div class="card">
      <figure>
        <img src="http://static.libsyn.com/p/assets/9/8/1/c/981c2ef87dd4c9e7/TCP000_thumbnail_v3.png" />
      </figure>
      <div>
        <div class="meta">
          <h2>Preference Media Queries</h2>
          <span class="time">15:40</span>
        </div>

        <div class="notes">
          <p class="desc">In this episode we narrow our focus on user-preference-based media queries, which enable you to create personalized experiences based on your users custom settings and needs.</p>
          <div class="links">
            <h3>Links</h3>
            <ul>
              <li>Media Queries → <a href="#">http://goo.gle/2MhYfR2</a></li>
              <li>Scripting → <a href="#">http://goo.gle/2Mdan5E</a></li>
              <li>The 'display-mode' media feature → <a href="#">http://goo.gle/2NoFr3c</a></li>
              <li>Prefers-* Security and Privacy → <a href="#">http://goo.gle/3kfwUM0</a></li>
              <li>CSS Color Adjustment → <a href="#">http://goo.gle/3qLkduJ</a></li>
            </ul>
          </div>
        </div>

        <button>Download Episode</button>
      </div>
    </div>
  </div>
</div>
<script>
    const parent = document.querySelector(".parent");
function onInput(e) {
  parent.style.width = `${e.target.value}px`;
}
</script>

```
출처 : https://codepen.io/una/pen/LYbvKpK

