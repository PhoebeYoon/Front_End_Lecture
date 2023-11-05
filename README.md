##### 🍑  Front_End 과정 1단계 

## aspect-ratio

### aspect-ratio: 3 /1  (2개의 값 지정)
엘리먼트의 크기를 지정할때 보토은 width, height를 지정한다. 만약 div태그에 아무 내용도 없는 상태에서 width만 지정한다면 화면에 표시되지 않는다. 왜냐하면 height를 지정하기 않았기 때문이다. 여기에 aspect-ratio :3/1 로 지정하고 개발자도구에서 확인해보면 height가 크기를 갖고 브라우저에 표시된다. 
```html
<style>
    div { width: 90px; background-color: orange; 
    /* height: 50px; */
    aspect-ratio: 3 /1 ;}
</style>
<div class="box"></div>
```

### aspect-ratio: 5 ( 1개의 값 지정)
```html
 <style>
div { width: 100px; background-color:teal;
aspect-ratio: 5 ;
 }
</style>
<div class="box"></div>
```
aspect-ratio: 5는  5 / 1로 높이를 1로 간주한다 그러니까 width가 100px 이면 height는 1/5인 20픽셀이다. 

### aspect-ratio:auto 1 /1 ( auto를 사용할 경우)
지정된 엘리먼트에 고유의 비율이 지정되어 있지 않다면 1 /1 로 , 비율이 지정되어 있다면 auto 로 작동한다.  

```html
<style>
        body { display: flex; gap:20px}
        .box-1 { background-color: teal;
                 width: 100px;  aspect-ratio: auto 1 /1;}
        .box-2 { width: 100px;  aspect-ratio: auto 1 /1;}
        .box-3 { width: 100px;  aspect-ratio: auto 1 /1;}
</style>
<div>
    <h4>A. 종횡비 1/1 적용</h4>
    <div class="box-1"></div>
</div>
<div>
    <h4>B. 종횡비 auto 적용</h4>
    <img class="box-2" src="https://place-hold.it/300x500/ddd"/>
  </div>
<div>
    <h4>C. 종횡비 1/1 적용</h4>
    <img class="box-3" src=https://place-hold.it/300x500/ff0"/>
</div>
```
같은 스타일을 적용했을때 A는 자체의 비율을 갖고 있지 않기 때문에 1/1로  작동한다.  
B는 이미 비율이 존재하기 때문에 auto가 작동하여  width:100px를 300 /500의 비율에 맞춰서 조절된다 (100 x 166.66 )   
C도 자신의 비율대로 B처럼 100 x 166.66으로 조절된다. 만약 auto를 지우면 1/1 이 적용되어서 100px X 100px로 바뀐다 



