##### 🍑  Front_End 과정 1단계 


## min() | max()

min(a, b,...) 함수는 쉼표로 구분된 값 목록에서 가장 작은 값을 속성 값으로 사용합니다
max(a, b, ...) 함수는 쉼표로 구분된 값 목록에서 가장 큰 값을 속성 값으로 사용합니다
```css
 /* width: 70%; max-width: 600px; */ <--이것은 width를 70%로 하되 최대 600px이면
                          600px 이상으로는 너비를 늘리지 않는다는 전통적인 방식이고
                         이것을 아래와 같이 한 문장으로 고칠 수 있다.
   width: min(500px, 70%);
  여기에 min()대신 max()를 사용하면 아래와 같다
  width: max(90%, 700px); // 700px이상이면 90%로 크기를 설정한다 
```

```html
 <style>
    * { box-sizing: border-box; margin: 0;}
    :root { --clr-primary:#ee6352;  --clr-body:#333;  --clr-bg:#ddd; }
    body { 
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        line-height: 1.6;
        color:var(--clr-body);
        background: var(--clr-bg);
    }
    .content { background: white; 
    padding: 3em;
    box-shadow: 0 0 3em rgba(0,0,0,0.15); 
    /* width: 70%;
    max-width: 600px; */
    width: max(60%, 700px);
}
.title { margin: 0 0 0.5em; font-weight: 900; color:var(--clr-primary)  }
 p {
 /* font-size:4vw ;  */
 /* 위의 내용으로,  화면이 500px  font-size는 20px, 화면이 250px일때   font-size:10px 이 된다*/

font-size: max(16px, 4vw);
/* 이렇게 하면 화면이 클때 4vw로 계산되지만 화면이 작아지더라도  font-size:16px 이하로는 작아지지 않는다 */
}
</style>
    <div class="content">
        <h2 class="title">A catchy title here</h2>
        <p >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nesciunt,
cum sequi voluptas assumenda nam dolores dolore a quos possimus </p>
    </div>


```

