##### 🍑  Front_End 과정 1단계 

## position 설정
모든 엘리먼트는 기본적으로 static 으로 설정되어 있다. 이것은 not positioned로 아직 포지션되지 않았다는 의미이다. 
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




