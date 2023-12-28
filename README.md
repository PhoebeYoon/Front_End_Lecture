##### 🍑  Front_End 과정 1단계 

## position 설정
모든 엘리먼트는 기본적으로 **static** 으로 설정되어 있다. 이것은 **not positioned로 아직 포지션되지 않았다는 의미이다.** 
그리고 normal 포지션은 relative 이다.  

어떤 엘리먼트가 포지션을 static에서 다른 것으로 바꾼다는 것은 움직이겠다는 의미이다.   
**마치 포지션을 부여받지 못한 야구선수는 playground에 입장할 수 없고, playground에 있다는 것은  포지션을 갖고 있다는 것처럼
그래서 .box { position:relative} 만 적는것은 의미가 없다**    

```html
<style>
.box_container { width: 300px; height: 500px; border: 2px solid;}
.box_container > div { width: 100px;height: 100px;}
.box-1 { background-color: tomato; 
    position: relative;
    /* right:-10px; */ /* 아래와 같은 방향으로 움직인다. */
    /* left:10px; */

    /* right:10px; */ /* 아래와 같은 방향으로 움직인다. */
    /* left:-10px; */
}

</style>
<div class="box_container">
    <div class="box-1"></div>
    <div class="box-2"></div>
    <div class="box-3"></div>
</div>
```

### position: relative
```css
.box-2 { background-color: tomato; 
    position: relative;
    left:4rem;
    bottom:2rem;
}
```  
box-2는 위아래에 있는 다른 엘리먼트에 의해 위치를 계산하고  
box-1, box-3는 box-2가 위치를 바꾸더라고 아무 영향없이 원래 자신의 위치를 지키고 있다는 것을 주목해야 한다.   


```css
<style>
.box_container { position: relative;}
.box-2 { background-color: tomato; 
    position: absolute;
    right:0rem;
    bottom:0rem;
}
</style>

```
위의 코드에서 부모에 relative를 주고 box-2에 absolute를 주면 
box-3이 box-1아래쪽으로 붙는다 위의 예제에서는 box-3은 여전히 box-2아래에 있고 box-1은 box-2위에 있었다.

이것은 마치 부모가 box-2는 따로 독립적으로 취급한다고 생각해야 한다.   

## width:auto 
위의 예에서 아래의 내용으로 바꿔보자. box-2의 너비를 브라우저의 크기에 자동으로 반응하게 하려고 한다.   
그런데 1번처럼 width:auto 로 주더라고 크기가 자동으로 변경되지 않는다. 스타일에서 2번처럼 주었기 때문이다.  
개발자도구에서 보면 .box-2의 width 속성이 취소선으로 되어 있다. 우선순위에서 밀린것이다.  
이때 3번처럼  우선순위를 낮춰주면 작동한다.  

```html
<style>
.box_container > div { width: 10rem; height: 10rem; } //2번
/* div { width: 10rem; height: 10rem; }  */ //3번
</style>

.box-2 { background-color: pink; // 1번
    position: fixed;
    width:auto;
    left:2rem;
    right:2rem;
    top:0rem;
}
```
<img width="600" alt="스크린샷 2023-12-28 오후 7 15 12" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/f2b7ec1b-9684-4f83-b1a8-6ff54ae81f63">

<img width="600" alt="스크린샷 2023-12-28 오후 7 14 29" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/cdbd27c0-c7fb-4ee4-b68d-87472374c6bd">








